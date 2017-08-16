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

在运行时中，Storyboard会创建一个<font color=#888>ViewController</font>的实例，它是你自定义的视图控制器的子类。Storyboard中的场景会出现在设备的屏幕上，且用户界面的行为是在<font color=#888>ViewController.swift</font>中定义的。

尽管，场景已经和<font color=#888>ViewController.swift</font>建立了连接，但这并不是唯一的连接。要在app中定义交互，你的视图控制器源代码需要与Storyboard中的视图进行通信。你可以在Storyboard中的视图和视图控制器源代码文件之间定义额外的连接(**outlets--连接插座** 和 **actions--行为**)来实现通信。

### 创建UI元素的Outlets

在代码文件里，[Outlets](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW55)提供了一种引用Storyboard中对象元素的方式。要创建一个outlet，请按住**Control**键将控件从Storyboard中拖拽到视图控制器文件中。此操作将在视图控制器文件里创建一个对象[属性](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW58)，它可以让你在运行时通过代码来访问和操纵。

你需要为用户界面中的text field和标签创建outlet，以便能够引用它们。

#### 将text field连接到ViewController.swift中

1. 打开你的Storyboard，<font color=#888>Main.storyboard</font>
2. 在Xcode工具栏右上角点击**Assistant**按钮，打开[辅助编辑器](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW76)。<br/><img src=Images/assistant_editor_toggle_2x-1.png width=307px>
3. 如果你想要获得更大的工作空间，可以通过点击Xcode工具条上的**Navigator**和**Utilities**按钮来折起[project navigator](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW57)(项目导航区)和[utility area](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW72)(工具区)区域。<br/><img src=Images/navigator_utilities_toggle_on_2x.png width=372px><br/>如有需要，你还可以折起[outline view](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW56)(大纲视图)。
4. 在辅助编辑器的顶部，点击**Automatic**-><font color=#888>ViewController.swift</font><br><img src=Images/CUIC_switchtoviewcontroller_2x.png width=680px><br><font color=#888>ViewController.swift</font>显示在辅助编辑器的右侧。
5. 在 <font color=#888>ViewController.swift</font>中，找到<font color=#888>class</font>一行，如下图：<br><img src=Images/class_2x.png width=320px>
6. 在<font color=#888>class</font>行下方输入如下代码：<br/><img src=Images/mark_2x.png width=154px><br/>你仅仅在源代码中填加了一条注释。[注释](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW31)在代码中只是一段文本，它不参与程序的编译，只是在个别地方提供解释说明的作用。<br/><font color=#888>//MARK:</font>是一种特殊的注释类型，它可以(阅读你代码的人)组织代码且帮助你快速定位代码的位置。稍后你会看到这一操作。此时，你所填加的这条注释表明，此处列出了属性列表。
7. 在Storyboard里选择text field。
8. 将text field从[场景](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW6)拖拽到右侧的代码编辑区内，停放在刚刚填加的注释下方。<br/><img src=Images/CUIC_textfield_dragoutlet_2x.png width=680px>
9. 在出现的对话框中，将<font color=#888>nameTextField</font>输入到**Name**栏中，其于选项保持默认。<br/><img src=Images/CUIC_textfield_addoutlet_2x.png width=680px>
10. 单击**Connect**<br/>Xcode将必要的代码添加到<font color=#888>ViewController.swift</font>中以存储对text field的引用，并配置Storyboard以设置该连接。<br/><img src=Images/CUIC1.png width=366px><br/>花一点时间来了解这行代码中发生了什么。<br/><font color=#888>IBOutlet</font>关键字告诉Xcode<font color=#888>nameTextField</font>属性关联自interface Builder(这也是为什么会有<font color=#888>IB</font>前缀的原因)。<font color=#888>weak</font>表明该属性是弱引用，不会发生无法释放的情况。弱引用可以预防循环引用；然而，为了保持对象在内存中处于活跃状态，你要确保app中的其他部分对它有强引用。在本课中，它是text field的父视图。父视图对所有子视图都持有强引用。只要父视图在内存中保持活跃，其子视图也会保持活跃。同理，视图控制器对其content view(内容视图)持有强引用，使整个视图层级保持在内存中。<br/>代码的其余部分定义了一个名为nameTextField的UITextField类型的[隐式解析可选]( https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW50)变量。请注意在类型声明结尾处的感叹号。感叹号表明此变量类型为隐式解析可选型，它是一个可选类型，它在第一次设值后总会有值。当你使用一个隐式解析可选类型时，系统会假定它有着正确的值且会自动为你解包。注意，如果变量的值没有设置，这将导致app终止运行。<br/>当从Storyboard中加载视图控制器时，系统会实例化视图层级结构，并给所有视图控制器的outlet分配适当的值。当视图控制器的<font color=#888>viewDidLoad()</font>方法被调用时，系统已将有效值分配给outlet，并且你可以安全访问它们的值。<br/>现在，用同样的方法将label与代码相连。

#### 将label连接到ViewController.swift

1. 在Storyboard里，选中label。
2. 将场景中的标签(label)拖拽到右侧的代码显示区，停留在刚刚填加的<font color=#888>nameTextField</font>属性的下方。<br/><img src=Images/CUIC_label_dragoutlet_2x.png width=680px>
3. 在出现的对话框中，将<font color=#888>mealNameLabel</font>输入到**Name**栏中，其于选项保持默认。<br/><img src=Images/CUIC_label_addoutlet_2x.png width=680px>
4. 单击**Connect**<br/>同样的，Xcode为<font color=#888>ViewController.swift</font>增加了必要的代码，并且存储了对label的引用，使代码和Storyboard建立了关联。这个outlet除了名字和类型以外和text field比较相似(这是UILabel类型的)。
