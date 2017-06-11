# [构建基本UI (Build a Basic UI)](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/BuildABasicUI.html#//apple_ref/doc/uid/TP40015214-CH5-SW1)

本课程让你熟悉Xcode，它是编写apps的工具。你将熟悉Xcode中的项目结构，学习如何在基本的项目控件之间导航和使用这些控件。在课程中，你将构建一个[用户界面(UI)](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW18)简单的**FoodTracker** app并且在模拟器上运行。完成后，你的app如下图所示：

<img src=Images/BBUI_sim_finalUI_2x.png width=387px>

## <font color=#888>学习目标 (Learning Objectives)</font>

在课程结束时，你将能够：  

* 在Xcode中创建项目
* 使用Xcode项目模版来创建一些关键的文件
* 打开项目且在文件之间切换
* 在模拟器上运行app
* 在storyboard中添加、移动和调整UI元素
* 使用属性检查器编辑UI元素的属性
* 在树形控件视图(outline view)中查看和排列UI元素
* 使用助手编辑器(Assistant editor)预览storyboard UI
* 使用自动布局(Auto Layout)来布置自动适应用户设备尺寸的用户界面

## <font color=#888>创建新项目 (Create a New Project)</font>

Xcode包含几个内置的app模版，用于开发常见类型的iOS app。例如游戏、基于标签的导航app和基于表视图的app。这些模版都具有预配置的界面和代码文件。本课中，你将从最基本的模版开始：单视图应用(Single View Application)

#### 创建新项目

1. 从/Applications目录打开Xcode。  
如果这是你第一次启动Xcode，它可能会要求你同意用户协议且下载一些其他组件。允许这些提示直到Xcode完全设置好并准备启动。  
一旦Xcode启动，便会呈现欢迎窗口。
<img src=Images/BBUI_welcomewindow_2x.png width=680px>

如果出现的是项目窗口而不是欢迎窗口，不要担心，因为你可能以前创建或打开过项目。只需要在下一步中使用菜单项创建项目即可。  
2. 在欢迎窗口中，点击“Create a new Xcode project” (或 choose File > New > Project)  
Xcode会打开一个新窗口并显示对话框，你可以选择一个模版。
3. 选择对话框顶部的iOS选项卡。  
4. 在Application部分中，选择Single View Application之后点击Next。
<img src=Images/BBUI_singleviewapp_template_2x.png width=680px>
5. 在显示的对话框中，使用以下值为你的app命名并选择其他额外选项：

* Product Name(产品名称): **FoodTracker**  
Xcode使用你输入的产品名称来命名你的产品和app。
* Team(团队)：如果这项没有自动填充，则选择None即可。
* Organization Name(组织名称)：组织的名称或自己的名称，此项可留空。
* Organization Identifier(组织标识符)：你组织的标识符。如果没有可以用**com.example**
* Bundle Identifier(捆绑标识符)：此值根据你的组织名称和组织标识符自动生成。
* Language(语言)：Swift
* Devices(设备)：通用
运行在iPhone和iPad上的通用app。
* Use Core Data(使用核心数据库)：未选择。
* Include Unit Tests(包含单元测试)：选择.
* Include UI Tests(包含UI测试)：未选择。
<img src=Images/BBUI_newproject_2x.png width=680px>

6 . 点击Next。  
7 . 在出现的对话框中，选择要保存项目的位置并点击Create。
Xcode在[workspace window](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW9)(工作窗口)中打开了新的项目。
<img src=Images/BBUI_workspacewindow_2x.png width=680px>

在工作窗口中，你可能会看到一个警告⚠️图标并显示一条信息：“Signing for FoodTracker requires a development team.”此警告表示你尚未设置开发团队，但不要担心，忽略这条警告也可以完成本课。你无需一个开发团队也可以在模拟器中运行app。

>进一步探索  
>**在iOS设备上运行app之前，你需要一个有效的小组以便对app进行签名。如果你是个体或苹果开发者计划的成员，你可以在此选择该小组。否则，你的Apple ID会分配给个人小组来启动设备上的app。然而，在你要提交app到App Store前，需要加入苹果开发者计划**
>**了解更多信息，请点击 Help 在搜索栏键入“Signing workflow.”**

## <font color=#888>熟悉Xcode (Get Familiar with Xcode)</font>

Xcode包含了创建一个app所需的一切。它组织了创建app的所有文件和资源。它为代码和用户界面提供了一些编辑器。并且，Xcode允许你构建、运行和调试你的app，且为模拟器和iOS设备提供了强大的调试器。  
花一点时间去熟悉Xcode工作区的主要部分。在整个课程中，你将使用下面窗口的区域。不要被这么多功能吓到，每个区域在需要使用的时候会有详细的说明。
<img src=Images/BBUI_workspacewindow_callouts_2x.png width=680px>

## <font color=#888>运行iOS模拟器 (Run iOS Simulator)</font>

因为你的项目基于Xcode模版，所以会自动为你设置好基本的应用程序环境。虽然你没有写任何代码，但是可以直接编译和运行单视图应用程序模版而无需其他配置。  
在Xcode里的iOS模拟器上编译并运行你的app。模拟器为你展现了你的app在真机设备上如何呈现页面外观和运行。  
模拟器可以模拟一些不同类型的硬件设备，包括所有屏幕尺寸和分辨率的iPad和iPhone。所以，你可以在每一个模拟设备上进行开发你的app。在本课中，使用iPhone7模拟器。

#### 在模拟器中运行你的app

1. 在Xcode工具栏的Scheme弹出菜单中选择iPhone7。  
Scheme弹出菜单允许你选择要运行app的模拟器或真机设备。确保你选的是iPhone7模拟器，而不是iOS设备。
<img src=Images/BBUI_schememenu_2x.png width=421px>

2. 点击位于Xcode工具条的左上角的Run按钮。
<img src=Images/BBUI_toolbar_2x.png width=680px>

或者选择 Product > Run (或按 Command + R)  
如果你第一次运行app，Xcode会询问你是否在Mac上启用开发者模式。开发者模式允许Xcode使用某些调试功能，而无需每次都输入密码。现在，根据提示决定是否启用开发者模式。
<img src=Images/BBUI_developermode_2x.png width=464px>

如果你不启用开发者模式，稍后可能会要求你输入密码。这些课程假设你已经启用了开发者模式。  
3. 随着编译进度的完成，观察Xcode工具条。  
在工具条的中间显示了编译进度的信息[activity viewer](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW24)。

在Xcode编译完成后，模拟器会自动启动。第一次启动模拟器可能要稍等片刻。  
在iPhone模拟器中启动你的app。起初，模拟器显示app的启动页面，随后转入主页面。在没有修改单视图程序模版的情况下，启动页面和主页面是相同的。
<img src=Images/BBUI_sim_blank_2x.png width=387px>

现在，单视图模版只是显示了白色屏幕，而其他模版具有更复杂的行为表现。在开发自己的app之前，了解每个模版的用途是十分重要的。不要修改模版，直接在模拟器中运行你的app，这是理解模版用途的好方法。

通过选择Simulator > Quit Simulator(或按Command-Q)退出模拟器。

## <font color=#888>查看源代码 (Review the Source Code)</font>

单视图模版包含几个设置应用程序环境的源代码文件。首先，来看看 <font color=#888>AppDelegate.swift</font> 这个文件。

#### 查看AppDelegate.swift源文件

1. 确保项目导航器在导航器区域中打开。<br/>[项目导航器(Project navigator)](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW57)显示了项目的所有文件。如果项目导航器未打开，请点击导航选择器最左侧的按钮。(或者，选择 View > Navigators > Show Project Navigator)<br/><img src=Images/BBUI_projectnavigator_2x.png width=478px>
2. 如有必要，通过点击项目导航器中的FoodTracker文件夹旁边的小三角来打开它。
3. 选择<font color=#888>AppDelegate.swift</font> 文件。<br/>Xcode在窗口主编辑区打开该源文件。<br/><img src=Images/BBUI_appdelegate_file_2x.png width=680px><br/>或者，双击<font color=#888>AppDelegate.swift</font>在一个单独的窗口中打开它。

### 应用程序代理源文件

<font color=#888>AppDelegate.swift</font> 源文件有2个主要功能：

* 定义了<font color=#888>AppDelegate</font>类。应用程序代理([app delegate](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW27))创建了窗口，该窗口中绘制了应用程序的内容，且提供了应用程序状态转换的场所。
* 为您的应用程序创建入口([entry point](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW37))，并为您的应用程序提供输入事件的运行循环([run loop](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW61))。这项工作是由<font color=#888>UIApplicationMain</font>属性(<font color=#888>@UIApplicationMain</font>)来完成的。该属性出现在文件的顶部。使用<font color=#888>UIApplicationMain</font>属性等同于调用<font color=#888>UIApplicationMain</font>函数，并将<font color=#888>AppDelegate</font>类的名称作为代理类的名称传递。作为响应，系统创建一个应用程序对象([application object](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW75))。应用程序对象负责管理应用程序的生命周期，系统还创建了一个<font color=#888>AppDelegate</font>类的实例，并将其分配给应用程序对象。最后，系统启动你的应用程序。

每当创建一个新项目时，都会自动创建<font color=#888>AppDelegate</font>类。除非你正在做一些非常不同寻常的事情，否则你应该使用Xcode提供的这个类来初始化应用程序并响应应用级别(app-level)的事件。<font color=#888>AppDelegate</font>类遵循<font color=#888>UIApplicationDelegate</font>协议。这个协议定义了一些用来设置应用程序的方法，来响应应用程序的状态变化，以及处理其他应用程序级别的事件。

<font color=#888>AppDelegate</font>类包含一个属性: <font color=#888>window</font>。

><font color=#A83690>var</font> <font color=#416E73>window</font><font color=#000>:</font> <font color=#5A2B95>UIWindow</font><font color=#000>?</font>

该属性存储着应用程序窗口的引用。此窗口代表了应用程序视图层级的根视图。这就是你所有的应用程序内容被绘制的地方。注意，窗口属性是可选([optional](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW11))的，这意味着在某个点可能没有值(为[nil](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW5))。

<font color=#888>AppDelegate</font>类还包含以下代理方法的实现:

<img src=Images/BBUI_code2.png>

这些方法让应用程序对象与应用程序代理进行通信。例如，在应用状态变化期间，应用启动，进入后台和应用终止——应用程序调用相应的代理方法，给应用程序一个响应的机会。你无需关心这些方法会不会在正确的时候被调用，应用程序对象会为你处理这些。

每个代理方法都有默认行为。如果你使用空模板或从<font color=#888>AppDelegate</font>类中删除了这些方法，那么每当调用该方法时，你会得到其默认的行为。

该模板为每个代理方法提供了注释。这些注释描述了你的应用程序如何使用这些方法。你可以使用这些方法和注释来设计出应用程序的蓝图。

在本节课中，你将不会使用任何自定义的协议代理代码，因此你不必对<font color=#888>AppDelegate.swift</font>文件进行任何更改。

### 视图控制器源文件

单视图模板还有另一个源文件：<font color=#888>ViewController.swift</font>。在项目导航器中选择<font color=#888>ViewController.swift</font>进行查看。
<img src=Images/BBUI_viewcontroller_file_2x.png width=680px>

这个文件定义了一个<font color=#888>UIViewController</font>的自定义[子类](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW14): <font color=#888>ViewController</font>。现在，这个类仅仅继承了<font color=#888>UIViewController</font>定义的所有行为。为了覆盖或扩展该行为，你将覆盖在<font color=#888>UIViewController</font>中定义的方法。

正如你在<font color=#888>ViewController.swift</font>中看到的。模板重写了<font color=#888>viewDidLoad()</font>和<font color=#888>didReceiveMemoryWarning()</font>方法；然而，这2个方法没有做任何事情，除了调用<font color=#888>UIViewController</font>的方法。你可以添加自己的代码来定制视图控制器对这些事件的响应。


尽管模板附带了<font color=#888>didReceiveMemoryWarning()</font>方法，但在这节课中无需实现它，所以可以将其删除。

现在，<font color=#888>ViewController.swift</font>文件的代码应该是这样：

<img src=Images/BBUI_code1.png>

你将在本课程后面的源代码文件中开始编写代码。

## <font color=#888>打开你的情节串联图板 (Open Your Storyboard)</font>

你现在可以在Storyboard上开始工作了。Storyboard是app用户界面的可视化表示，显示了屏幕的内容和它们之间的过渡转场。使用Storyboard来布置app流程。你可以在构建它时准确地了解自己正在构建的内容，或得及时反馈，了解哪些内容正在运行，哪些内容不可用，并对你的用户界面进行及时可见的更改。

#### 打开你的Storyboard

* 在项目导航栏中选择<font color=#888>Main.storyboard</font>。


