# [About Windows and Views](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/Introduction/Introduction.html)

在iOS中，可以使用Windows(窗口)和Views(视图)在屏幕上显示应用程序的内容。虽然窗口没有任何可见的内容，但是为应用程序的视图提供了一个基本的容器。视图定义了填充窗口的部分内容。例如，你可能会看到用来显示图像、文本、形状或其中一些组合的视图。你还可以使用视图来组织和管理其他视图。

## 概览(At a Glance)

每个应用程序都至少有一个窗口和一个视图来显示其内容。UIKit和其他系统框架提供了预先定义好的视图，可以用来显示内容。这些视图从简单的按钮(Button)和文本标签(label)到更复杂的视图，如表视图(tableView)、选择器视图(pickerView)和滚动视图(scrollView)。当预设的视图不足以满足需求时，可以自定义视图且管理其绘制和事件处理。

### 视图管理应用程序的可视内容

视图是[UIView](https://developer.apple.com/reference/uikit/uiview)类(或它的一个子类)的实例，并在应用程序窗口中管理一个矩形区域。视图负责绘制内容、处理多触摸事件和管理任何子视图的布局。绘图涉及到一些图像技术，例如Core Graphics，OpenGL ES，或UIKit。它们在视图的矩形区域中绘制图形，图像和文本。视图通过使用手势识别器( gesture recognizers)或直接处理触摸事件来对其矩形区域的触摸事件作出响应。在视图层级中，父视图负责定位和调整子视图，且可以动态调整。这种能够动态修改子视图的能力使你的视图能够适应不断变化的条件，例如界面的旋转和动画。

你可以将视图看作构建用户界面的模块。你通常使用多个视图来构建视图的层级，而不是使用一个视图来显示所有内容。层级中的每个视图都呈现用户界面的特定部分，通常针对特定类型的内容进行优化。例如，UIKit专门用于呈现图像、文本和其他类型的内容。

>相关章节：[View and Window Architecture](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/WindowsandViews/WindowsandViews.html#//apple_ref/doc/uid/TP40009503-CH2-SW1)，[Views](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/CreatingViews/CreatingViews.html#//apple_ref/doc/uid/TP40009503-CH5-SW1)

### 窗口协调视图的显示

窗口是[UIWindow](https://developer.apple.com/reference/uikit/uiwindow)类的一个实例，它可以处理应用程序用户界面的整体表现。Windows与Views(视图)来配合管理交互、变化以及视图的可见层级。在大多数情况下，应用程序的窗口不会发生变化。窗口被创建出来后，他将保持不变，直至显示的视图发生改变。每个应用程序都至少有一个窗口用来在设备的主屏幕上显示应用程序的用户界面。如果一个外接显示器连接到设备上，应用程序可以创建第二个窗口来显示该屏幕上的内容。
