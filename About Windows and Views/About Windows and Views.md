# [About Windows and Views (关于窗口和视图)](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/Introduction/Introduction.html)

在iOS中，可以使用Windows(窗口)和Views(视图)在屏幕上显示应用程序的内容。虽然窗口没有任何可见的内容，但是为应用程序的视图提供了一个基本的容器。视图定义了填充窗口的部分内容。例如，你可能会看到用来显示图像、文本、形状或其中一些组合的视图。你还可以使用视图来组织和管理其他视图。

## 概览 (At a Glance)

每个应用程序都至少有一个窗口和一个视图来显示其内容。UIKit和其他系统框架提供了预先定义好的视图，可以用来显示内容。这些视图从简单的按钮(Button)和文本标签(label)到更复杂的视图，如表视图(tableView)、选择器视图(pickerView)和滚动视图(scrollView)。当预设的视图不足以满足需求时，可以自定义视图且管理其绘制和事件处理。

### 视图管理应用程序的可视内容 (Views Manage Your Application’s Visual Content)

视图是[UIView](https://developer.apple.com/reference/uikit/uiview)类(或它的一个子类)的实例，并在应用程序窗口中管理一个矩形区域。视图负责绘制内容、处理多触摸事件和管理任何子视图的布局。绘图涉及到一些图像技术，例如Core Graphics，OpenGL ES或UIKit。它们在视图的矩形区域中绘制图形、图像和文本。视图通过使用手势识别器( gesture recognizers)或直接处理触摸事件来对其矩形区域的触摸事件作出响应。在视图层级中，父视图负责定位和调整子视图，且可以动态调整。这种能够动态修改子视图的能力使你的视图能够适应不断变化的条件，例如界面的旋转和动画。

你可以将视图看作构建用户界面的模块。通常使用多个视图来构建视图的层级，而不是使用一个视图来显示所有内容。层级中的每个视图都呈现了用户界面的特定部分，通常会针对特定类型的内容进行优化。例如，UIKit专门用于呈现图像、文本和其他类型的内容。

>相关章节：[View and Window Architecture](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/WindowsandViews/WindowsandViews.html#//apple_ref/doc/uid/TP40009503-CH2-SW1)，[Views](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/CreatingViews/CreatingViews.html#//apple_ref/doc/uid/TP40009503-CH5-SW1)

### 窗口协调视图的显示 (Windows Coordinate the Display of Your Views)

窗口是[UIWindow](https://developer.apple.com/reference/uikit/uiwindow)类的一个实例，它可以处理应用程序用户界面的整体表现。Windows与Views(视图)来配合管理交互、变化以及视图的可见层级。在大多数情况下，应用程序的窗口不会发生变化。窗口被创建出来后，他将保持不变，直至显示的视图发生改变。每个应用程序都至少有一个窗口用来在设备的主屏幕上显示应用程序的用户界面。如果一个外接显示器连接到设备上，应用程序可以创建第二个窗口来显示该屏幕上的内容。

>相关章节：[Windows](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/CreatingWindows/CreatingWindows.html#//apple_ref/doc/uid/TP40009503-CH4-SW1)

### 动画为用户提供了界面变化的可见反馈 (Animations Provide the User with Visible Feedback for Interface Changes)

动画为用户提供关于视图层次结构变化的可见反馈。系统定义了标准的动画，用于表示模态视图(presenting modal views)和不同视图组之间的转换。然而，视图的许多属性也可以直接进行动画。例如，通过动画你可以改变视图的透明度，在屏幕上的位置，大小，背景色或其他属性。如果直接使用视图的底层(Core Animation)核心动画层对象，那么你也可以执行许多其他的动画。

>相关章节：[Animations](https://developer.apple.com/library/content/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/AnimatingViews/AnimatingViews.html#//apple_ref/doc/uid/TP40009503-CH6-SW1)

### 界面构造器的作用 (The Role of Interface Builder)


Interface Builder是一个应用程序，用于以图形方式构建和配置应用程序的窗口和视图。使用Interface Builder，你可以组合视图并将它们放在一个nib文件中，该文件是一个资源文件，用于存储视图和其他对象的freeze-dried版本。当你在运行时加载[nib](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/LoadingResources/CocoaNibs/CocoaNibs.html#//apple_ref/doc/uid/10000051i-CH4)文件时，其内部的对象将重构为实际对象，你可以以纯代码的方式进行对它们进行操作。Interface Builder极大简化了创建应用程序用户界面所需要做的工作。由于Interface Builder和nib文件贯穿了整个iOS，所以在你设计应用程序时需要用nib文件。

有关如何使用Interface Builder的更多信息，请参阅*see Interface Builder User Guide*(界面构建器用户指南)。有关视图控制器如何管理包含视图的nib文件信息，请参阅在[View Controller Programming Guide for iOS](https://developer.apple.com/library/content/featuredarticles/ViewControllerPGforiPhoneOS/index.html#//apple_ref/doc/uid/TP40007457)(iOS的视图控制器编程指南)中创建自定义内容视图控制器。

### 参阅 (See Also)

因为视图是非常复杂多变的对象，在这一个文档中想要涵盖所有的视图行为是不可能的。所以，其他文档可以帮助你了解和管理视图及用户界面的其他方面。
* 视图控制器(View controllers)是管理应用程序视图的重要部分。视图控制器在单一视图层级中管理所有视图，使它们更容易在屏幕上呈现。有关视图控制器及其作用的更多信息，请参阅[View Controller Programming Guide for iOS](https://developer.apple.com/library/content/featuredarticles/ViewControllerPGforiPhoneOS/index.html#//apple_ref/doc/uid/TP40007457)。
* 视图是应用程序中手势和触摸事件的关键响应者。有关使用手势识别器和处理触摸事件的更多信息，请参阅[Event Handling Guide for UIKit Apps](https://developer.apple.com/library/content/documentation/EventHandling/Conceptual/EventHandlingiPhoneOS/index.html#//apple_ref/doc/uid/TP40009541)(UIKit应用程序的事件处理指南)。
* 自定义视图必须使用可用的绘图技术来呈现其内容。有关使用这些绘图技术的信息，请参阅[Drawing and Printing Guide for iOS](https://developer.apple.com/library/content/documentation/2DDrawing/Conceptual/DrawingPrintingiOS/Introduction/Introduction.html#//apple_ref/doc/uid/TP40010156)(iOS绘图和打印指南)。
* 在标准视图动画不足以满足需求时，你可以使用Core Animation(核心动画)。有关使用Core Animation实现动画的信息，请参阅[Core Animation Programming Guide](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/CoreAnimation_guide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40004514)(核心动画编程指南)。

Updated: **2014-09-17**
