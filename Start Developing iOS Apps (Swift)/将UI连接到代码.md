# [将UI连接到代码 (Connect the UI to Code)](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/ConnectTheUIToCode.html#//apple_ref/doc/uid/TP40015214-CH22-SW1)

在本课中，你将把**FoodTracker** app的基本[用户界面](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW18)与代码相连，并且定义一些用户可以在界面中执行的行为。完成后，你的app将如下所示：

<img src=Images/CUIC_sim_finalUI_2x.png width=387px>

## <font color=#888>学习目标 (Learning Objectives)</font>

在课程结束时，你将能够：

* 解释Storyboard中场景和底层视图控制器的关系。
* 在界面元素和代码之间创建outlet连接插座和行为。
* 从text field中处理用户输入且在UI中显示结果。
* 使类遵循某个协议。
* 理解代理(delegation)模式。
* 在设计app架构时，遵从目标-动作(target-action)模式。

## <font color=#888>将UI连接到源代码 (Connect the UI to Source Code)</font>

[Storyboard](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW8)中的元素和源代码是有关联的。理解Storyboard和代码之间的关系是非常重要的。

在Storyboard中，一个[场景](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW62)代表一个屏幕上的内容，通常是一个视图控制器。在视图控制器里可以实现app的各种行为。[视图控制器](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW7)管理一个带有子视图层级结构的单一内容视图。视图控制器在app的数据模型和视图之间起着协调数据流的作用。它封装了这些数据且用视图去显示出来。视图控制器管理着视图的生命周期，处理设备方向的旋转，定义app的导航和相应用户的输入行为。iOS中的所有视图控制器对象都是<font color=#888>UIViewController</font>类或它的一个子类。

通过创建和实现自定义视图控制器[子类](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW14)来定义视图控制器的行为。然后，你可以在Storyboard中创建这些类和场景之间的连接，以获得在代码中定义的行为以及在Storyboard中定义的用户界面。

正如之前看到的，Xcode已经创建了一个这样的类，<font color=#888>ViewController.swift</font>，它已经与你现在工作的这个场景建立了关联。将来，当你添加更多场景时，你将在身份检查器中自行创建此关联。[身份检查器](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW80)允许你在与该对象的身份相关的Storyboard中编辑对象的属性，例如对象所属的类。

<img src=Images/CUIC_inspector_identity_2x.png width=272px>