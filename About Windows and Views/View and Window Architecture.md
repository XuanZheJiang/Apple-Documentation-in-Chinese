# [View and Window Architecture (视图和窗口架构)](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/WindowsandViews/WindowsandViews.html#//apple_ref/doc/uid/TP40009503-CH2-SW1)

视图和窗口显示您的应用程序的用户界面，并处理与该界面的交互。UIKit和其他系统框架提供了许多视图，你可以按原样使用，几乎不需要修改。你也可以在需要展示不同内容的地方自定义视图，而不是局限于系统给定的标准视图。

无论你使用系统视图还是创建自己的自定义视图，你都需要了解由[UIView](https://developer.apple.com/reference/uikit/uiview)和[UIWindow](https://developer.apple.com/reference/uikit/uiwindow)类提供的基础结构。这些类为管理视图的布局和展示提供了复杂的工具。