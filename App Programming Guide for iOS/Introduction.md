# [App Programming Guide for iOS](https://developer.apple.com/library/content/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40007072)
---
## 有关iOS App架构

Apps需要与iOS协同合作，以确保它们能提供出色的用户体验。除了优秀的设计和用户界面之外，优秀的用户体验还包含了许多其他因素。用户期望iOS apps在能够快速响应的同时尽可能降低耗电。Apps需要支持所有最新的iOS设备，同时这款应用看起来就是为当前设备量身定制的。起初，要实现这些行为看起来是令人生畏的，但iOS提供了你需要的帮助。
<img src=Images/ios_pg_intro_2x.png width=490px>

本文突出讲解了让app在iOS上运行良好的核心行为。你可能没有实现文中描述的每个特性，但你应该为每个创建的项目考虑这些特性。

>**注意**：
>iOS应用的开发需要一个基于英特尔的Macintosh电脑，并安装了iOS SDK。有关如何获得iOS SDK的信息，请访问[iOS Dev Center](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=891bd3417a7776362562d2197f89480a8547b108fd934911bcbea0110d07f757&path=%2Fdownload%2F&rv=1)(iOS开发中心)。

## 概览

当你准备好将你的想法转化为app时，你需要了解系统和app之间的交互作用。
