# 普通控件

## 文本框

#### 外观

![](input-text.jpg)

* 在同一个表单内，所有的文本框最好是等宽的。
* 多行文本或者长度过长文本，请使用Textarea。
* 在PC上的使用难度要远远低于移动端，所以移动端要慎用文本框。
* 所有的文本框都应该设定好Placeholder。

### 常见自定义实现

##### 字数提示

在input框右侧显示文本框的最大字符长度和当前字符长度，有很好辅助提示效果，用户体验良好。如下图：
![](/assets/input-text-charater-counter.jpg)

在多个项目中均有实现，可以封装为Angular的directive或者component。

## 下拉框

* 不要用默认select控件样式，太丑。
* 默认的下拉控件适合展示4-9条选项，如果超过9个选项，最好增加选项搜索功能，参照[特殊控件](/form/advanced_form_control.md)
* 如果选项少于4项，请选择radio button控件。
* 不要使用支持多选的下拉框，使用checkbox控件。
* 下拉列表的排序，建议采用按照被选中的可能性排序。
* 

