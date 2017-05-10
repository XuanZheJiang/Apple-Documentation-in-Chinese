# [UIButton](https://developer.apple.com/reference/uikit/uibutton)

#### UIButton对象是一个视图，它可以根据用户的交互来执行特定代码。

---

## 简介

当你点击或选中按钮后，它会响应附加在它身上的动作。你可以使用label(标签)、image(图片)或同时使用来达到与按钮通讯的目的。按钮的外观配置是可以更改的。因此，你可以渲染按钮或格式化标题使其设计风格与app匹配。你可以使用Interface Builder(可视化界面构造器)或纯代码的方式给用户交互界面增加按钮。

<img src=Images/uibutton.png width=100px>

在界面上添加一个按钮时需执行以下步骤：
* 创建时指定一个按钮类型。
* 给按钮提供一个标题字符串或图片，并设置合适的尺寸大小。
* 给按钮关联一个或多个行为方法。
* 设置Auto Layout(自动布局)规则，以控制界面中按钮的大小和位置。
* 提供可访问信息和局部字符串。

有关基本视图的更过信息，请访问[View Programming Guide for iOS](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/Introduction/Introduction.html#//apple_ref/doc/uid/TP40009503)

## 按钮反馈

当用户点击按钮后，按钮使用[Target-Action](https://developer.apple.com/library/content/documentation/General/Conceptual/Devpedia-CocoaApp/TargetAction.html#//apple_ref/doc/uid/TP40009071-CH3)(目标-动作)设计模式通知你的app。你无需直接处理按钮的触摸事件，而是为按钮指定行为方法，并指定某些触发事件去调用某些方法。在runtime(运行时)中，按钮处理所有传入的触摸事件，并调用关联的方法来响应。  
使用[addTarget(_:action:for:)](https://developer.apple.com/reference/uikit/uicontrol/1618259-addtarget)方法给按钮关联一个行为或在Interface Builder(可视化界面构造器)里创建一个关联行为。行为方法采用Listing1里列出的一种方法来关联。选择提供您需要响应按钮的信息的表单。
**Listing 1**按钮的行为方法
`@IBAction func doSomething()`
`@IBAction func doSomething(sender: UIButton)`
`@IBAction func doSomething(sender: UIButton, forEvent event: UIEvent)`

## 配置按钮的外观

按钮的类型定义了其基本外观和行为。在创建按钮时，使用[init(type:)](https://developer.apple.com/reference/uikit/uibutton/1624028-init)方法或在storyboard里指定其类型。按钮的类型一旦创建则无法更改。通常会使用**Custom**和**System**类型，但在适当的时候也可使用其他类型。

>**注意**  
>要配置app中所有按钮的外观，请使用appearance proxy object(外观代理对象)。UIButton类实现了[appearance()](https://developer.apple.com/reference/uikit/uiappearance/1615010-appearance)类方法，在app中，你可以使用它来获取所有按钮的外观代理。

## 按钮状态

按钮使用5种状态来定义外观：default，highlighted，focused，selected，disabled。当你在界面中添加一个按钮时，它处于default状态，这意味着按钮是激活的，用户没有与其交互。当用户与按钮进行交互时，其状态将会更改为其他值。例如，当用户点击带有标题的按钮时，按钮会变为highlighted状态。

以纯代码或Interface Builder(可视化界面构造器)配置按钮时，要分别为每个状态指定属性。如果你没有为某个特定的状态指定属性，那么UIButton类会提供合理的默认状态。例如，disabled状态的按钮通常会变暗且点击时不会变为highlighted状态。这个类的其他属性，如[adjustsImageWhenHighlighted](https://developer.apple.com/reference/uikit/uibutton/1624031-adjustsimagewhenhighlighted)和[adjustsImageWhenDisabled properties](https://developer.apple.com/reference/uikit/uibutton/1624020-adjustsimagewhendisabled)属性，让你在特定情况下改变默认行为。

## 内容

按钮的内容由你指定的标题字符串或图像组成。指定的内容用来配置按钮自身的[UILabel](https://developer.apple.com/reference/uikit/uilabel)和[UIImageView](https://developer.apple.com/reference/uikit/uiimageview)对象。你可以使用[titleLabel](https://developer.apple.com/reference/uikit/uibutton/1623992-titlelabel)或[imageView](https://developer.apple.com/reference/uikit/uibutton/1624033-imageview)属性来获取这些对象且修改它们的值。这个类也为配置字符串或图像提供了一些(convenient shortcut)方便的快捷方式。

通常，使用标题或图像来配置按钮，并相应地对按钮大小进行调整。按钮还可以有一个背景图像，它位于你指定内容的后面。可以为按钮指定图像和标题，这将导致如图2所示的外观。你可以使用指定的属性访问按钮的当前内容。

**图2**为按钮提供标题和图像

<img src=Images/uibutton_figure2.png width=377px>

在设置按钮的内容时，必须分别指定每个状态的标题、图像和外观属性。如果你不为某个特定的状态定制内容，则按钮使用与(Default)默认状态想关联的值，并添加任何适当的自定义。例如，在highlighted状态下，如果没有提供自定义图像，基于图像的按钮将在默认图像的顶部绘制一个区域高亮显示。

## 颜色渲染

你可以使用[tintColor](https://developer.apple.com/reference/uikit/uibutton/1624025-tintcolor)属性指定按钮的颜色。该属性设置按钮图像和文本的颜色。如果你没有明确指定其颜色，按钮就会使用父视图的颜色。

## 边缘嵌入(Edge Insets)

使用insets在你的自定义或系统按钮中，添加或删除内容周围的空间。你可以分别指定按钮标题([titleEdgeInsets](https://developer.apple.com/reference/uikit/uibutton/1624010-titleedgeinsets))或图片([imageEdgeInsets](https://developer.apple.com/reference/uikit/uibutton/1624034-imageedgeinsets))的insets(边缘)，也可以一起修改边缘([contentEdgeInsets](https://developer.apple.com/reference/uikit/uibutton/1624036-contentedgeinsets))。当应用时，会影响按钮的矩形内容，该按钮使用Auto Layout(自动布局)来确定其位置。

你应该没有理由去调整按钮的信息、联系或去纰漏它。

## 可视化界面构造器的属性(Interface Builder Attributes)

表1列出了在Interface Builder中为按钮配置的核心属性。

**表1** 核心属性

|属性|描述|
|:---|---|
|Type(类型)|按钮类型。这个属性决定了许多其他按钮的默认设置。该属性不能在(runtime)运行时修改，但可以使用[buttonType](https://developer.apple.com/reference/uikit/uibutton/1624011-buttontype)来获取按钮的类型|
|State Config(状态配置)|状态选择器。在这个状态配置中选择一个值后，按钮属性的更改将应用到指定状态。|
|Title(标题)|按钮的标题。你可以将按钮的标题指定为普通字符串或带属性的字符串(attributed string)|
|Title Font and Attributes(标题字体和属性)|应用于按钮标题上的字体和其他属性。具体的配置选项取决于你是否为按钮的标题指定了一个普通字符串或带属性的字符串。对于普通字符串，你可以定制字体、文本颜色和阴影颜色。对于带属性的字符串，你可以指定对齐方式、字体方向、缩进、断字和许多其他选项。|
|Image(图像)|按钮的前景图像。通常，你可以使用模版图像作为按钮的前景图像，也可以使用Xcode项目中指定的任何图像。|
|Backgroud(背景)|按钮的背景图像。背景图像显示在标题和前景图像后面。|

表2列出了影响按钮外观的属性。

**表2** 外观属性

|属性|描述|
|:---|---|
|Shadow Offset(阴影偏移量)|按钮阴影的偏移量和行为。阴影只影响标题字符串。在勾选了**Reverses on Highlight**选项时，当按钮状态更改为高亮或从高亮显示状态更改时，标题阴影会突出显示<br>用纯代码方式配置阴影偏移量，可以使用按钮[titleLabel](https://developer.apple.com/reference/uikit/uibutton/1623992-titlelabel)对象的[shadowOffset](https://developer.apple.com/reference/uikit/uilabel/1620528-shadowoffset)属性。配置高亮行为可以使用[reversesTitleShadowWhenHighlighted](https://developer.apple.com/reference/uikit/uibutton/1624004-reversestitleshadowwhenhighlight)属性。|
|Drawing(绘图)|按钮的绘图行为。<br>开启[shows TouchWhenHighlighted](https://developer.apple.com/reference/uikit/uibutton/1623996-showstouchwhenhighlighted)选项后，当用户点击按钮时，在按钮上会增加一个白色光晕。<br>开启[adjusts ImageWhenHighlighted](https://developer.apple.com/reference/uikit/uibutton/1624031-adjustsimagewhenhighlighted)选项后，按钮图像在highlighted状态下会变暗。<br>开启[adjusts ImageWhenDisabled](https://developer.apple.com/reference/uikit/uibutton/1624020-adjustsimagewhendisabled)选项后，当按钮被禁用(disabled)时图像会变暗。|
|Line Break(换行符)|按钮文本的换行选项。使用这个属性来定义按钮的标题是如何修改的，以适应可用的空间。|

表3列出了按钮的edge inset(边缘嵌入)属性。使用edge inset按钮可以改变按钮的矩形内容。

**表3** 边缘嵌入属性
|属性|描述|
|:---|---|
|Edge(边缘)|配置边缘嵌入。你可以指定按钮整体内容的边缘，也可以分别指定按钮的标题或图像的边缘。|
|Inset(嵌入)|边缘值。正值会收缩边缘靠近按钮中心，负值会扩大边缘远离按钮中心。在runtime(运行时)使用[contentEdgeInsets](https://developer.apple.com/reference/uikit/uibutton/1624036-contentedgeinsets)，[titleEdgeInsets](https://developer.apple.com/reference/uikit/uibutton/1624010-titleedgeinsets)和[imageEdgeInsets](https://developer.apple.com/reference/uikit/uibutton/1624034-imageedgeinsets)属性来获取这些边缘值。|

要了解关于按钮继承属性的更多信息，请参阅[UIControl](https://developer.apple.com/reference/uikit/uicontrol)和[UIView](https://developer.apple.com/reference/uikit/uiview)。

## 国际化(Internationalization)

要国际化一个按钮，请为按钮的标题文本指定一个本地化的字符串。(你也可以指定适当的本地化图像)

当使用storyboard来构建界面时

## 符号
