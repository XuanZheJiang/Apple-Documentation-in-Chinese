# [View and Window Architecture (视图和窗口架构)](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/WindowsandViews/WindowsandViews.html#//apple_ref/doc/uid/TP40009503-CH2-SW1)

视图和窗口显示您的应用程序的用户界面，并处理与该界面的交互。UIKit和其他系统框架提供了许多视图，你可以按原样使用，几乎不需要修改。你也可以在需要展示不同内容的地方自定义视图，而不是局限于系统给定的标准视图。

无论你使用系统视图还是创建自己的自定义视图，你都需要了解由[UIView](https://developer.apple.com/reference/uikit/uiview)和[UIWindow](https://developer.apple.com/reference/uikit/uiwindow)类提供的基础结构。这些类为管理视图的布局和展示提供了复杂的工具。了解这些工具如何工作对你在应用程序中恰当的使用视图是很重要的。

## 视图架构基础 (View Architecture Fundamentals)

你想完成大部分可视内容的时候，都是使用视图对象([UIView](https://developer.apple.com/reference/uikit/uiview)类的实例)来完成的。一个视图对象在屏幕上定义了一个矩形区域,处理绘图和触摸事件。一个视图也可以作为其他视图的父视图且可以调整其位置和大小。UIView类的大部分工作都在管理这些视图之间的关系,但是你也可以根据需要自定义默认的行为。你也可以在需要的地方自定义视图的默认行为。

<img src=Images/view-layer-store.jpg width=326px>