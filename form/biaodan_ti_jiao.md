#表单提交
###提交方式
无特殊情况下，表单提交采取POST方式。(延伸阅读: [POST vs GET](http://www.w3schools.com/tags/ref_httpmethods.asp))
###提交过程
所有AJAX方式的表单提交，在提交过程中应显示[Loading效果](../common/loading_animation.md)
###回车触发
确保用户在录入表单的过程中，随时可以通过**回车键触发表单提交**（重要的用户习惯与体验），我们来看看如何实现: (如果想看各种情况下的回车提交表单，[请点这里](https://www.oschina.net/question/1092_25864))

* 当表单中只有一个文本输入框，当用户在输入框中输入完毕，直接回车即可触发表单提交。这种情况一般是搜索功能。

```
<form>
<input type="text" placeholder="输入后回车">
</form>
```

* 当表单中不仅只有一个文本输入框时，需要在表单中增加一个type=submit的按钮，那么在表单内任何输入框中敲击回车，都会触发表单提交

```
<form>
<input type="text" name="text1" placeholder="输入后回车">
<input type="text" name="text2" placeholder="输入后回车">
<textarea name="textarea" placeholder="输入后回车"></textarea>
<input type="submit"/>
</form>
```

###防止重复提交。
表单重复提交是在Web应用中非常常见、历史悠久、带来很多麻烦的一个问题。尤其是在创建表单中，非常容易导致重复记录，想象一下，如果“确认支付”的按钮，没有在前台和后台进行任何重复提交的判断，用户手一抖就有可能会导致最终被剁手的惨剧...OK, 我们先看一下都会有哪些会导致用户重复提交的场景：

* 点击提交按钮两次。
* 提交后点击浏览器刷新按钮。
* 使用浏览器后退按钮重复之前的操作，导致重复提交表单。
* 使用浏览器历史记录重复提交表单。
*用户提交表单时可能因为网速的原因导致提交过程过慢，用户再次提交。
    
看到这些场景我们就可以了解，我们需要在前台和后台同时处理重复提交的情况。前台的常见处理方式有：

* 提交后立刻显示Loading动画，确保覆盖提交按钮，防止用户连续俩次点击提交按钮，例如：


![](http://segmentfault.com/img/bVb2OM) 

* 同时设置提交按钮的disabled，可以使按钮失效。

<input type="submit" disabled>

```
//原生HTML的写法
<input type="submit" disabled>

//Angular2的写法
<button type="submit" [disabled]="!ngForm.valid">Submit</button>

//Angular1的写法
<button ng-disabled="checked">Button</button>

//jQuery的写法
//看了原生HTML写法不会jQuery, 需要好好学习前端。
```

  * 为了防止用户连续敲击回车，导致重复提交的情况。需要通过额外的JS变量来判断提交流程是否正在处理，通过变量来防止重复提交。

更为重要的后台处理方式，不仅能防止用户无意的误操作，还能起到阻止恶意攻击的效果：

1. 首先，根据业务规则，在数据库里添加唯一约束或创建唯一索引，防止出现重复数据。这是最根本最有效的防止重复提交数据的方法。
2. Post -> Redirect -> Get, 将Post方式的表单提交，通过服务器Redirect到一个Get方式的URL, 这样可以避免刷新页面、返回上一页这些方式导致的重复提交。
3. 表单隐藏的唯一token方式，每次表单都包含一个随机生成的一次性token，服务器端判断token只能一次性使用。




