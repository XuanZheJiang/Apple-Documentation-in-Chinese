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
* 使用属性观察器编辑UI元素的属性
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

Xcode在[界面构建器](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW47)(Interface Builder)中打开Storyboard，它的可视化界面编辑器在编辑器区域。Storyboard的背景是[画布](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW6)(canvas)。你可以使用画布来添加和排列用户界面元素。

你的Storyboard应该和这个相似：

<img src=Images/BBUI_storyboard_empty_2x.png width=680px>


现在，Storyboard包含一个[场景](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW62)(scene)，它展现了app屏幕的内容。指向画布左侧的箭头是Storyboard的[起始点](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW66)(storyboard entry point)，这意味着app启动时，这个场景首先被加载。现在，你在画布上看到的场景包含了一个被视图控制器管理的视图。你将很快了解视图及视图控制器的作用。
当你在iPhone7模拟器上运行app时，这个场景中的视图就是你在设备屏幕上看到的。然而，画布中的场景大小可能和模拟器屏幕的尺寸不同，你可以在场景的底部选择屏幕尺寸和方向。在本例中，都采用iPhone7的尺寸和竖直方向，所以画布和模拟器是一样的。

尽管画布显示了一个特定的设备和方向，但是创建一个可以自适应的界面是很重要的，使它在任何设备和任何方向上看起来都是很好的。当你在开发界面时，你可以修改画布的视图，以便看到你的界面是如何适应不同尺寸的屏幕。

## <font color=#888>构建基本UI (Build the Basic UI)</font>

是时候构建一个基本界面了。你将从场景中的一个用户界面开始，在餐饮跟踪程序“FoodTracker”中增加新餐。

Xcode提供了一个可以添加到Storyboard文件的对象库。其中一些是出现在用户界面中的元素，如按钮和文本字段。其他的，比如视图控制器和手势识别器，定义了应用程序的行为，但不会在屏幕上出现。

在用户界面中出现的元素称为视图。视图显示内容给用户。它们是构建用户界面的模块，以一种清晰、优雅和有用的方式呈现内容给用户。视图有许多有用的内置行为，包括在屏幕上显示自己，并对用户输入作出反应。

iOS中的所有视图对象都是UIView或它的一个子类，许多UIView的子类在外观和行为方面都是高度定制的。首先添加一个text field(<font color=#888>UITextField</font>),一个UIView的子类，到你的场景。TextField允许用户输入一行文本，你将使用该文本作为用餐的名称。

#### 在场景中新增一个TextField

1. 选择Editor > Canvas 并确保**Show Bounds Rectangles**是选中状态。<br/>此设置可以使画布中的所有视图周围都绘制一个蓝色边框。许多视图和控件的背景都是透明的，以至于很难看清它们的实际大小。当系统调整其大小超出或小于预期值时会发生布局错误。开启此设置有助于你了解视图的层级结构。
2. 打开对象库<br/>[对象库](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW54)在Xcode右侧底部的[工具区](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW72)。如果没看到，请点击对象库选择栏(Library selector bar)的第三个按钮(Object library)。(或者选择 View > Utilities > Show Object Library。)<br/><img src=Images/object_library_2x.png width=438px><br/>列表中显示了每个对象的名称、描述和可视化表示。
3. 在对象库底部的过滤栏中输入<font color=#888>text field</font>来快速找到Text Field对象。
4. 将Text Field对象从对象库拖到场景中。<br/><img src=Images/BBUI_textfield_drag_2x.png width=446px><br/>如有必要，通过Editor > Zoom对画布进行缩放。
5. 拖动text field使其位于场景的上半部分，并与场景的左边距对齐。<br/>当你看到如下画面时停止拖动。<br/><img src=Images/BBUI_textfield_place_2x.png width=418px><br/>蓝色参考线帮助你放置text field。当你拖动或调整对象尺寸接近边界时，参考线才会显示，直至松手后才会消失。
6. 如有必要，请点击text field来显示调整自身尺寸的拖拽点。<br/>你可以通过拖拽界面元素的[尺寸拖拽点](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW60)(resize handles)来调整其大小。尺寸拖拽点是围绕在元素边界上的白色小方块。你可以通过点击元素来显示尺寸拖拽点。在本课中，text field应该已被选中，应为你已经停止拖动了。如果你的text field如下图所示，则可以调整其尺寸了。否则，在画布中选中它则可以显示拖拽点。<br/><img src=Images/BBUI_textfield_resizehandles_2x.png width=415px>
7. 调整text field的左右边距直到看到三条垂直参考线：左边距对齐，水平中心对齐和右边距对齐。<br/><img src=Images/BBUI_textfield_finalsize_2x.png width=414px><br/>虽然在场景中有了text field，但是没有提示用户要输入什么。使用text field的占位符文本(placeholder)来提示用户输入菜名。

#### 配置text field的占位符文本

1. 选中text field，在工具区(utility area)打开属性观察器<img src=Images/inspector_attributes_2x.png width=16px>(Attributes inspector)。<br/>当你在检查器选择栏中单击左边的第四个按钮时出现[属性观察器](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW19)。它可以让你在Storyboard中编辑某个对象的属性。<br/><img src=Images/BBUI_inspector_attributes_2x.png width=419px><br/>
2. 在属性观察器中找到Placeholder字样的输入框，并输入<font color=#888>Enter meal name</font>。

>进一步探索<br/>
><font color=#000>在app的发布版本中，用户看到的任何字符串(比如text field的占位符文本)都应进行本地化。欲了解更多信息，请参阅[Build Apps for the World](https://developer.apple.com/internationalization/)</font>

**3**. 按下Return键在text field中显示新的占位符文本。<br/>你的场景应类似这样：

<img src=Images/BBUI_textfield_withplaceholder_2x.png width=680px>

在编辑text field的属性时，还可以编辑用户选择text field时弹出的系统键盘的属性。

#### 配置text field的键盘

1. 确保text field仍是选中状态。
2. 在属性观察器中找到**Return Key**字段且选择**Done**选项(如有需要可向下滚动)。<br/>此更改将把键盘的返回键由默认(default)改为了完成(Done)，使返回键更加明显。
3. 在属性观察器中勾选**Auto-enable Return Key**复选框(如有需要请再次向下滚动)。<br/>此更改使用户在未输入任何字符前，返回键是灰色且无法点击的，确保了不会输入一个空的名称用作用餐名。

属性观察器现在应该显示如下键盘设置：<br/><img src=Images/BBUI_keyboardattributes_2x.png width=272px><br/>

接下来，在场景顶部添加一个标签(UILabel)。标签不是交互式的，它只能在用户界面显示静态文本。为了帮助你了解如何在用户界面中定义元素之间的交互，你将配置此标签来显示用户在text field中输入的文本。此方法可以很好的测试text field捕获用户输入的文本且进行适当的处理。

#### 在场景中新增一个标签

1. 在对象库的过滤栏中输入<font color=#888>label</font>来快速找到UILabel对象。
2. 将标签对象拖到场景中。
3. 在场景中拖动标签对象，使其在text field的上面，并与text field的左边界对齐。<br/>如下图所示时，停止拖动：<br/><img src=Images/BBUI_label_place_2x.png width=420px><br/>
4. 双击标签对象且输入 <font color=#888>Meal Name</font>。
5. 按下Return键在标签对象中显示新文本。<br/>现在，在场景中增加一个按钮(UIButton)对象。按钮是可交互的，因此，用户可以点击它来触发自定义行为。之后，你将创建一个操作，将标签文本重设为默认值。

#### 在场景中新增一个按钮

1. 在对象库的过滤栏中输入<font color=#888>button</font>来快速找到按钮对象。
2. 将按钮对象拖到场景中。
3. 在场景中拖动按钮对象，使其在text field的下面，并与text field的左边界对齐。<br/>如下图所示时，停止拖动：<br/><img src=Images/BBUI_button_place_2x.png width=422px><br/>
4. 双击按钮对象且输入 <font color=#888>Set Default Label Text</font>。
5. 按下Return键在按钮对象中显示新文本。
6. 如有必要，请重新调整按钮。

现在，场景看起来应该是这样的：

<img src=Images/BBUI_button_rename_2x.png width=417px>

在场景中添加的元素都是可见的，这有助于理解这些元素。通过大纲(outline)视图来查看在场景中已添加的元素。

#### 查看大纲视图

1. 在Storyboard中，找到大纲视图的开关(Outline view toggle)。<br/><img src=Images/BBUI_outlineview_toggle_2x.png width=px680><br/>
2. 如果大纲视图是折叠状态，请单击Outline view toggle来展开大纲视图。

[大纲视图](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW56)在画布的左侧，它可以让你看到Storyboard中对象的层级关系。你应该能够看到刚刚添加的text field、标签和按钮在层次结构中。但为什么你刚刚添加的元素都被嵌套在View下？

View不仅能够在屏幕上显示自己和对用户输入作出反应，它还可以充当其他视图的容器，View排列在视图层级结构中。[视图层级](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW21)定义了视图相对于其他视图的布局。在层级结构中，视图中包含的视图称为[子视图](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW22)(subviews)，而包含它的视图称为[父视图](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW67)(superview)。视图可以有多个子视图，但只能有一个父视图。

<img src=Images/BBUI_outlineview_2x.png width=243px>

总之，每个场景都有其自身的视图层级。在每个视图层级的顶层是[容器视图](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW34)。当前场景中，容器视图名为**View**，它是View Controller中的顶层视图。text field、标签和按钮都是容器视图的子视图。你在此场景中放置的所有视图都是容器视图的子视图(尽管它们本身也会有子视图)。

## <font color=#888>预览界面 (Preview Your Interface)</font>

定期预览你的app，已检查一切是否符合你的预期。你可以使用[辅助编辑器](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW76)(assistant editor)来预览app的界面，它会在主编辑窗口旁并排显示第二个编辑窗口。

#### 预览界面

1. 单击Xcode右上角附近Xcode工具栏中的辅助编辑按钮以打开辅助编辑器。<br/><img src=Images/assistant_editor_toggle_2x.png width=307px>
2. 如果想要更大的工作空间，请单击Xcode工具栏中的导航器(Navigator)和工具(Utilities)按钮，以此来折叠项目导航区和工具区。<br/><img src=Images/navigator_utilities_toggle_on_2x.png width=372px><br/>你也可以将大纲视图折叠起来。
3. 在辅助编辑器顶部的编辑选择栏中，将辅助编辑器从**Automatic**切换至**Preview > Main.storyboard (Preview)**<br/><img src=Images/BBUI_assistant_editorselectorbar_2x.png width=680px><br/><img src=Images/BBUI_assistant_editorselectorbarpreview_2x.png width=680px><br/>正如你在辅助编辑器所看到的，预览界面看起来几乎和画布界面是一样的。然而，它们没有什么不同的。画布界面和预览界面的屏幕尺寸(iPhone 7)和屏幕方向(纵向)都是一致的。如果你想检查界面是否是自适应的，你需要预览不同尺寸的屏幕尺寸和方向。<br/><img src=Images/BBUI_preview_same_2x.png width=680px>
4. 要预览横向，请单击预览界面底部的预览按钮。<br/><img src=Images/BBUI_preview_rotatebutton_2x.png width=389px><br/>不幸的是，这一切似乎有点不对劲，text field、标签和按钮在左上角还保持着相同的尺寸和位置。这意味着text field的尺寸不再是填充两侧的边缘。<br/><img src=Images/BBUI_preview_rotated_2x.png width=680px>
5. 要预览不同尺寸的屏幕，请单击辅助编辑器底部的增加按钮，然后选择iPhone SE。<br/><img src=Images/BBUI_preview_addSE_2x.png width=680px><br/>同样，text field、标签和按钮还在左上角。然而，这一次text field的长度超出了屏幕的右边界。<br/><img src=Images/BBUI_preview_small_2x.png width=334px>

要创建自适应界面，你需要指定界面在不同屏幕上如何调整。例如，当界面旋转至横向时，text field应该增长。当屏幕尺寸时SE时，text field应该收缩。你可以使用自动布局(Auto Layout)来轻松指定这些规则。

## <font color=#888>采用自动布局 (Adopt Auto Layout)</font>

[自动布局](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW77)是一个强大的布局引擎，它可以帮助你设计适合于对场景大小变化做出动态响应的自适应布局。你可以使用[约束](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/GlossaryDefinitions.html#//apple_ref/doc/uid/TP40015214-CH12-SW78)(constraints)来描述一个元素相对于另一个元素的位置，元素的尺寸，或者哪个应该先收缩。自动布局根据这些约束动态计算每个元素的大小和位置。

定义约束最简单的方式是使用堆叠视图(UIStackView)。StackView提供了一个简化的界面，用于在列或行中布局视图集合。StackView使用自动布局来计算它所管理的所有视图的尺寸和位置。这样可以轻松地使用自动布局的全部功能，同时大大减少布局的复杂性。

采用自动布局封装现有的界面元素，然后在场景中给StackView添加约束。

#### 为用餐场景添加约束

1. 通过单击标准按钮返回标准编辑器(Standard editor)。<br/><img src=Images/standard_toggle_2x.png width=371px><br/>通过Xcode工具栏中的导航按钮和工具按钮展开项目导航器和工具区。
2. 按住Shift键的同时选择text field、标签和按钮。<br/><img src=Images/BBUI_AL_shift_select_2x.png width=680px>
3. 在画布右下角，单击**Embed In Stack**(嵌入堆叠视图)按钮(或者选择**Editor > Embed In > Stack View**)。<br/><img src=Images/BBUI_AL_stackmenu_2x.png width=680px><br/>Xcode在堆叠视图中包裹了界面的元素，将它们堆叠在一起。Xcode分析你现有的布局，以确定使用垂直堆叠，而不是水平堆叠。<br/><img src=Images/BBUI_AL_stack_2x.png width=680px>
4. 如有需要，打开大纲视图，选择堆叠视图。<br/><img src=Images/BBUI_AL_outlineview_2x.png width=243px>
5. 在属性观察器中，找到**Spacing**字段，输入**8**，按下**Return**键。<br/>你会注意到用户界面元素垂直间距在增大，而堆叠视图随它们一起增大。<br/><img src=Images/BBUI_AL_stackspaced_2x.png width=418px>
6. 在画布右下角，打开**Add New Constraints**菜单。<br/><img src=Images/BBUI_AL_pinmenu_2x.png width=680px>
7. 在**Spacing to nearest neighbor**的上方，单击2个水平约束和顶部垂直约束，当你选中时，它们会变成红色。<br/><img src=Images/BBUI_AL_pinconstraints_2x.png width=284px><br/>这些约束表示了距离周围最近元素左边、右边和顶部的间距。最近元素可以是父视图、其他元素或页面边缘。