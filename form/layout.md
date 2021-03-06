# 表单的外观

### 布局

* 表单的标题统一展示在页面左上方。

* 表单的按钮展示在右下角（或居中，统一即可），按钮的大小、排放顺序和对应的颜色需要统一，需要通过颜色和摆放位置区分主要操作按钮和次要操作按钮。

* 表单中所有字段的label右对齐，label与input框中间是否有“：”符号需要统一。

* 提供舒适的点击区域。无论你所设计的是网页还是APP，都应当考虑用户在手机上点击屏幕时的体验。你需要确保用户点击输入框的时候的触发区域足够宽松舒适，而不是很难点击。一般说来，拇指的触发区域应当控制在 45~57px之间，但是在移动端上，控件看起来太大会让人觉得不舒服，所以你的文本框高度应该设计在32~40px之间，这样看起来足够友好，又不会太大。

  ![](/assets/1-a1DUx27CoT1XaMXCHh42CQ.jpeg)

### 文字

* 表单中label字体需要加粗（font- weight）。
* 在设置字体尺寸的时候，应该确保字体足够大，尽量让它们清晰可辨。网页上设置正文字体的时候，最安全的选择是16px，当然，大小的选取主要还是取决于实际的页面设计，如果识别性问题，应当适当调大一些。

  ![](/assets/1-HEpft_aPpJOljFQoO7uQlQ.jpeg)

* 永远不要使用全部是大写字母的文本标签，这样的标签通常都很难快速浏览，因为字母的大小高度都是一致的，对于非英语言国家的用户尤其麻烦。![](/assets/1-1US1eP1h7gFl-QFPTWjC0A.png)

### 提示

* 表单用于搜集不同类型的用户输入，所有必填项字段的label前（或后，统一即可）需要显示红色的“\*”。不过登录表单可以不遵循这个规则，大家都知道登录表单中的标签项均为必填，同时也可以根据标签项是否输入的状态来激活「登录」按钮。

* 一列布局的表单，页面错误提示信息在数据右侧展示；多列布局的表单，页面错误提示信息在数据下方展示。

* 帮助信息（或相关文字）应当出现在需要的地方，比如表单中用文字说明为何需要填写信用卡号，以及生日日期填写之后的福利，又或者“服务条款”链接的存在。它们适时地出现，帮助用户解释了一些令人困惑的问题。一般说来，这类帮助信息最好不要超过100字。

### 样式

* 表单中正在被编辑的控件展示阴影效果（box-shadow）。![](/assets/焦点.png)

* 表单中禁用信息展示为整个编辑框置灰（disabled），鼠标滑过展示禁止操作的icon（not-allowed）。Disabled对于所有的表单元素都有效，包括select, radio, checkbox, button等，当用户提交表单时，这个表单输入项不会被提交。适应场景如下：

* 用户按了提交按钮后，利用javascript将提交按钮disabled掉，这样可以防止用户反复提交也可以减少服务器的压力。

* 用户提交表单信息需要管理员审批时（此时不允许用户更改表单数据）， 因为disable左右范围大，一般使用disable。![](/assets/1.png)

* 表单中只读信息同样展示为整个编辑框置灰（readonly），但仍保留标准的鼠标状态。Readonly只针对input\(text / password\)和textarea有效，当用户提交表单时，该输入项会作为form的一项被提交。适应场景如下：

  在某个表单中为用户预填了某个唯一识别代码，不允许用户改动，但是在提交时需要传递该值，此时应该将它的属性设置为readonly。

  ![](/assets/readonly.png)

### 焦点

* 表单录入页面，需要把输入焦点定位到第一个输入项。用户通过Tab键可以在输入框或操作按钮间切换，并注意Tab的操作应该遵循从左向右、从上而下的顺序。

* 表单字段较多需要滚动页面才能看到完整表单信息时，用户提交表单报错最好定位到错误的锚点位置，节省用户寻找的时间。多个字段报错时，定位到第一个错误位置。

### 按钮/链接文字/图标

* 当按钮标签过长（超过6个中文字），导致视觉出现问题时，建议改用链接文字。

* 当按钮嵌在文本中时，应该用链接文字。

* 当命令是次要时，应该用链接文字。

* 当命令是很常规的操作（如删除、编辑等），且图标语义非常容易理解时，可以使用图标作为操作按钮。

### 

### 

### 



