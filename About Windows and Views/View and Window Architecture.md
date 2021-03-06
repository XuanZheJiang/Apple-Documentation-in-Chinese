# [View and Window Architecture (视图和窗口架构)](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/WindowsandViews/WindowsandViews.html#//apple_ref/doc/uid/TP40009503-CH2-SW1)

视图和窗口显示您的应用程序的用户界面，并处理与该界面的交互。UIKit和其他系统框架提供了许多视图，你可以按原样使用，几乎不需要修改。你也可以在需要展示不同内容的地方自定义视图，而不是局限于系统给定的标准视图。

无论你使用系统视图还是创建自己的自定义视图，你都需要了解由[UIView](https://developer.apple.com/reference/uikit/uiview)和[UIWindow](https://developer.apple.com/reference/uikit/uiwindow)类提供的基础结构。这些类为管理视图的布局和展示提供了复杂的工具。了解这些工具如何工作对你在应用程序中恰当的使用视图是很重要的。

## 视图架构基础 (View Architecture Fundamentals)

你想完成大部分可视内容的时候，都是使用视图对象([UIView](https://developer.apple.com/reference/uikit/uiview)类的实例)来完成的。一个视图对象在屏幕上定义了一个矩形区域来处理绘图和触摸事件。一个视图也可以作为其他视图的父视图且可以调整其子视图的位置和大小。<font color=#888>UIView</font>类的大部分工作都在管理这些视图之间的关系,但是你也可以根据需要自定义默认的行为。

视图与核心动画层(Core Animation Layer)一起协同工作，以处理视图内容的渲染和动画。UIKit中的每个视图都有一个层(通常是CALayer类的实例)对象，它为视图提供存储支持并处理与视图相关的动画。你应该通过<font color=#888>UIView</font>来处理大多数的操作。但是，在你需要对视图的渲染或动画行为进行更多控制的情况下，您可以通过它的layer(层)来执行操作。

要理解视图和层之间的关系，可以查看一个示例。如图1-1
显示来自视图转场([ViewTransitions](https://developer.apple.com/library/content/samplecode/ViewTransitions/Introduction/Intro.html#//apple_ref/doc/uid/DTS40007411))示例应用程序的视图体系结构以及与底层核心动画层的关系。图1-1 中的应用程序包括一个窗口(Window)(也是一个视图)一个通用的<font color=#888>UIView</font>对象，它充当一个容器视图，一个图像视图(image view)，一个用于显示控件的工具栏(toolbar)和一个工具栏按钮(bar button item)(按钮本身不是一个视图，而是管理其内部的视图)。

<img src=Images/view-layer-store.jpg>
