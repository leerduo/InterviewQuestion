# InterviewQuestion

工作原因，不再更新。

整理的常见的问题   http://chenfuduo.cn

[整理来自这里](https://github.com/android-cn/android-discuss)

水平有限，有错误请提出来。


# Android常见的问题

标签（空格分隔）： 移动开发

---
> * 常见算法问题的 Java 实现



[资料可见](https://github.com/pedrovgs/Algorithms)

[算法介绍可见](http://blog.csdn.net/v_JULY_v)

算法是很多公司面试必须，国内 BAT 基本面试中都会有，尤以百度为盛。


----------

> * 常见设计模式的 Java 实现

[资料可见](https://github.com/iluwatar/java-design-patterns)


----------

> * Android 开源项目源码解析


[资料可见](http://www.codekk.com)

Android 开源项目源码解析网页版。反正只要是面高级开发者，我都会问他项目中使用的库原理，这是我对高级开发者一般的要求。

国内中大型的公司及优秀创业公司都比较看重原理，重知其然知其所以然。


----------

> * 遇到问题你可以@的那些 Android 开发者



碰到问题，首先我们建议 Google，无果可 @ GitHub 上的 Android 开发者(好像我暴露他们了( ⊙ o ⊙ ))。

* [Android 开源交流群成员](https://github.com/orgs/aosp-exchange-group/people)

* [android-cn 成员](https://github.com/orgs/android-cn/people)

* [部分不错的国内外开发者](https://github.com/android-cn/android-dev-cn)

* [部分不错的国外开发者](https://github.com/android-cn/android-dev-com)


----------

> * Java 基础之 String、StringBuilder、StringBuffer、CharSequence 区别

两个比较好的回答：

> NO1

1) CharSequence接口:是一个字符序列.String StringBuilder 和 StringBuffer都实现了它.
2) String类:是常量,不可变.
3) StringBuilder类;只可以在单线程的情况下进行修改(线程不安全).
4) StringBuffer类:可以在多线程的情况下进行改变(线程安全).
5)Stringbuilder比StringBuffer效率高,应该尽量使用StringBuilder.

> NO2

1.CharSequence是一个java接口，代表一个char序列，String、StringBuilder、StringBuffer都实现了该接口，CharSequence实例通过调用toString方法可转化为String对象。
2.String类是final的，不可派生子类，其内部封装的是char[]，另外，android下的String类和jdk中的String类是有区别的，android下的String类中部分API通过native方法实现，效率相对高一些。
3.String使用'+'进行字符串拼接时，在编译期会转化为StringBuilder#append方式
4.String在内存中有一个常量池，两个相同的串在池中只有一份实例(String s = "abc"方式或者String#intern方式会在池中分配)，使用new String方式会在heap中分配，每次创建都是一个全新的实例。
5.StrigBuilder & StringBuffer都是可扩展的串，提供了一系列apped方法用于拼接不同类型对象
6.StringBuffer于jdk1.0引入，线程安全（多线程场景下使用），StringBuilder于jdk1.5引入，线程不安全，因而效率更高。
7.StringBuilder & StringBuffer初始容量都为16，开发者应该指定其容量，以避免多次扩容所带来的性能问题。


----------


> * Java 基础之继承与接口的区别


* 抽象类：

抽象类体现了数据抽象的思想，是实现多态的一种机制。它定义了一组抽象的方法，至于这组抽象方法的具体表现形式由派生类来实现。同时抽象类提供了继承的概念，它的出发点就是为了继承，否则它没有存在的任何意义。所以说定义的抽象类一定是用来继承的，同时在一个以抽象类为节点的继承关系等级链中，叶子节点一定是具体的实现类。
在语法方面：
1.由abstract关键词修饰的类称之为抽象类。
2.抽象类中没有实现的方法称之为抽象方法，也需要加关键字abstract。
3.抽象类中也可以没有抽象方法，比如HttpServlet方法。
4.抽象类中可以有已经实现的方法，可以定义成员变量。

* 接口：
接口是用来建立类与类之间的协议，它所提供的只是一种形式，而没有具体的实现。同时实现该接口的实现类必须要实现该接口的所有方法，通过使用implements关键字。 接口是抽象类的延伸，java为了保证数据安全是不能多重继承的，也就是说继承只能存在一个父类，但是接口不同，一个类可以同时实现多个接口，不管这些接口之间有没有关系，所以接口弥补了抽象类不能多重继承的缺陷，
语法方面：
1.由interface关键词修饰的称之为接口；
2.接口中可以定义成员变量，但是这些成员变量默认都是public static final的常量。
3.接口中没有已经实现的方法，全部是抽象方法。
4.一个类实现某一接口，必须实现接口中定义的所有方法。
5.一个类可以实现多个接口。

区别：
一.语法层次上：如上所述。
二.设计层次上：
1、 抽象层次不同。抽象类是对类抽象，而接口是对行为的抽象。抽象类是对整个类整体进行抽象，包括属性、行为，但是接口却是对类局部（行为）进行抽象。
2、 跨域不同。抽象类所跨域的是具有相似特点的类，而接口却可以跨域不同的类。我们知道抽象类是从子类中发现公共部分，然后泛化成抽象类，子类继承该父类即可，但是接口不同。实现它的子类可以不存在任何关系，共同之处。例如猫、狗可以抽象成一个动物类抽象类，具备叫的方法。鸟、飞机可以实现飞Fly接口，具备飞的行为，这里我们总不能将鸟、飞机共用一个父类吧！所以说抽象类所体现的是一种继承关系，要想使得继承关系合理，父类和派生类之间必须存在"is-a" 关系，即父类和派生类在概念本质上应该是相同的。对于接口则不然，并不要求接口的实现者和接口定义在概念本质上是一致的， 仅仅是实现了接口定义的契约而已,相当于是"like-a"的关系。
3、 设计层次不同。对于抽象类而言，它是自下而上来设计的，我们要先知道子类才能抽象出父类，而接口则不同，它根本就不需要知道子类的存在，只需要定义一个规则即可，至于什么子类、什么时候怎么实现它一概不知。比如我们只有一个猫类在这里，如果你这是就抽象成一个动物类，是不是设计有点儿过度？我们起码要有两个动物类，猫、狗在这里，我们在抽象他们的共同点形成动物抽象类吧！所以说抽象类往往都是通过重构而来的！但是接口就不同，比如说飞，我们根本就不知道会有什么东西来实现这个飞接口，怎么实现也不得而知，我们要做的就是事前定义好飞的行为接口。所以说抽象类是自底向上抽象而来的，接口是自顶向下设计出来的。

附加，空接口的作用:
通常是作为一个标记，你比如这个Serializable、Cloneable。


----------

> * Android开发中何时使用多进程



要想知道如何使用多进程，先要知道Android里的多进程概念。一般情况下，一个应用程序就是一个进程，这个进程名称就是应用程序包名。我们知道进程是系统分配资源和调度的基本单位，所以每个进程都有自己独立的资源和内存空间，别的进程是不能任意访问其他进程的内存和资源的。那如何让自己的应用拥有多个进程？很简单，我们的四大组件在AndroidManifest文件中注册的时候，有个属性是`android:process`:

* 这里可以指定组件的所处的进程。默认就是应用的主进程。指定为别的进程之后，系统在启动这个组件的时候，就先创建（如果还没创建的话）这个进程，然后再创建该组件。你可以重载Application类的onCreate方法，打印出它的进程名称，就可以清楚的看见了。再设置android:process属性时候，有个地方需要注意：如果是android:process=":deamon"，以:开头的名字，则表示这是一个应用程序的私有进程，否则它是一个全局进程。私有进程的进程名称是会在冒号前自动加上包名，而全局进程则不会。一般我们都是有私有进程，很少使用全局进程。他们的具体区别不知道有没有谁能补充一下。[源文档地址](http://developer.android.com/intl/zh-cn/guide/topics/manifest/service-element.html#proc)

* 使用多进程显而易见的好处就是分担主进程的内存压力。我们的应用越做越大，内存越来越多，将一些独立的组件放到不同的进程，它就不占用主进程的内存空间了。当然还有其他好处，有心人会发现Android后台进程里有很多应用是多个进程的，因为它们要常驻后台，特别是即时通讯或者社交应用，不过现在多进程已经被用烂了。典型用法是在启动一个不可见的轻量级私有进程，在后台收发消息，或者做一些耗时的事情，或者开机启动这个进程，然后做监听等。还有就是防止主进程被杀守护进程，守护进程和主进程之间相互监视，有一方被杀就重新启动它。应该还有还有其他好处，这里就不多说了。

* 坏处的话，多占用了系统的空间，大家都这么用的话系统内存很容易占满而导致卡顿。消耗用户的电量。应用程序架构会变复杂，应为要处理多进程之间的通信。这里又是另外一个问题了。


----------

> * 设备横竖屏切换的时候，接下来会发生什么

我们一般看到的答案：

* 不设置Activity的android:configChanges时，切屏会重新调用各个生命周期，切横屏时会执行一次，切竖屏时会执行两次


* 设置Activity的android:configChanges="orientation"时，切屏还是会重新调用各个生命周期，切横、竖屏时只会执行一次


* 设置Activity的android:configChanges="orientation|keyboardHidden"时，切屏不会重新调用各个生命周期，只会执行onConfigurationChanged方法

这个是不完整的。下面的文字引自Android Developer：

> Caution: Beginning with Android 3.2 (API level 13), the `"screen size" `also changes when the device switches between portrait and landscape orientation. Thus, if you want to prevent runtime restarts due to orientation change when developing for API level 13 or higher (as declared by the minSdkVersion and targetSdkVersion attributes), you must include the "screenSize" value in addition to the "orientation" value. That is, you must decalare android:configChanges="orientation|screenSize". However, if your application targets API level 12 or lower, then your activity always handles this configuration change itself (this configuration change does not restart your activity, even when running on an Android 3.2 or higher device).

也就是说：当API >12时，需要加入screenSize属性，否则屏幕切换时即使你设置了orientation系统也会重建Activity.

[横竖屏切换对生命周期的影响](http://developer.android.com/guide/topics/resources/runtime-changes.html)

[Activity在清单文件中的属性](http://developer.android.com/guide/topics/manifest/activity-element.html#config)


----------

> * 要做一个尽可量流畅的ListView，你可以做到的优化手段是什么？越详细越多手段越好

* 复用convertView
* 使用ViewHolder
* item中有图片时，异步加载
* 快速滑动时，不加载图片
* item中有图片时，应对图片进行适当压缩
* 分批和分页加载

[facebook新闻页ListView优化](http://blog.aaapei.com/article/2015/02/facebookxin-wen-ye-listviewyou-hua)


----------

> * java虚拟机的运行原理

[参见这里的文档](http://chenfuduo.me/categories/JVM/)


----------

> * 继承viewGroup后必须实现哪些方法，这些方法有谁调用

继承ViewGroup后，IDE会提示提供构造方法和实现`onLayout()`方法。


在ViewGroup中只有一个抽象的方法`onLayout()`，所以必须实现它；如果执行`requestLayout()`请求重新调整位置会调用到`onLayout()`。

[ViewGroup深入理解](http://blog.csdn.net/androidstarjack/article/details/42788383)

----------

> * android 关于安全的问题，你所知道的所有的安全问题

 - 错误导出组件
 - 参数校验不严
 - WebView引入各种安全问题
 - 不混淆、不防二次打包
 - 明文存储关键信息
 - 错误使用HTTPS
 - 山寨加密方法

[Security Tips](http://developer.android.com/intl/zh-cn/training/articles/security-tips.html)


----------

> * 对称加密和非对称加密

对称加密，就是加密和解密数据都是使用同一个key，这方面的算法有DES。
非对称加密，加密和解密是使用不同的key。发送数据之前要先和服务端约定生成公钥和私钥，使用公钥加密的数据可以用私钥解密，反之。这方面的算法有RSA。ssh 和 ssl都是典型的非对称加密。

[对称加密](http://baike.baidu.com/view/119320.htm)
[非对称加密](http://baike.baidu.com/view/1490349.htm)


----------

> * Activity的四种launchMode



Activity一共有以下四种launchMode：

> * standard
> * singleTop
> * singleTask
> * singleInstance


我们可以在AndroidManifest.xml配置的android:launchMode属性为以上四种之一即可。
下面我们结合实例一一介绍这四种lanchMode：
1.standard
standard模式是默认的启动模式，不用为配置android:launchMode属性即可，当然也可以指定值为standard。standard启动模式，不管有没有已存在的实例，都生成新的实例。

2.singleTop
我们在上面的基础上为指定属性android:launchMode="singleTop"，系统就会按照singleTop启动模式处理跳转行为。跳转时系统会先在栈结构中寻找是否有一个Activity实例正位于栈顶，如果有则不再生成新的，而是直接使用。如果系统发现存在有Activity实例,但不是位于栈顶，重新生成一个实例。
这就是singleTop启动模式，如果发现有对应的Activity实例正位于栈顶，则重复利用，不再生成新的实例。

3.singleTask
如果发现有对应的Activity实例，则使此Activity实例之上的其他Activity实例统统出栈，使此Activity实例成为栈顶对象，显示到幕前。

4.singleInstance
这种启动模式比较特殊，因为它会启用一个新的栈结构，将Acitvity放置于这个新的栈结构中，并保证不再有其他Activity实例进入。


----------

> * Android启动Service的两种方式是什么? 它们的适用情况是什么

* startService：生命周期与调用者不同。启动后若调用者未调用stopService而直接退出，Service仍会运行
* bindService：生命周期与调用者绑定，调用者一旦退出，Service就会调用unBind->onDestroy


----------


> * 谈谈你对Android中Context的理解

[参考下面的文章](http://blog.csdn.net/qinjuning/article/details/7310620)


----------

> * Java中反射的作用是什么?什么时候会用到


JAVA反射机制是在#运行时#，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法；这种动态获取的信息以及动态调用对象的方法的功能称为java语言的反射机制。
Java反射机制主要提供了以下功能：
a)在运行时判断任意一个对象所属的类；
b)在运行时构造任意一个类的对象；
c)在运行时判断任意一个类所具有的成员变量和方法；
d)在运行时调用任意一个对象的方法；生成动态代理。


----------

> * 注册广播有几种方式，这些方式有何优缺点？请谈谈Android引入广播机制的用意


1.在清单文件中注册， 常见的有监听设备启动，常驻注册不会随程序生命周期改变
2.在代码中注册，随着程序的结束，也就停止接受广播了


Android引入广播机制的用意:

ａ:从MVC的角度考虑(应用程序内)
其实回答这个问题的时候还可以这样问，android为什么要有那4大组件，现在的移动开发模型基本上也是照搬的web那一套MVC架构，只不过是改了点嫁妆而已。android的四大组件本质上就是为了实现移动或者说嵌入式设备上的MVC架构，它们之间有时候是一种相互依存的关系，有时候又是一种补充关系，引入广播机制可以方便几大组件的信息和数据交互。

b：程序间互通消息(例如在自己的应用程序内监听系统来电)

c：效率上(参考UDP的广播协议在局域网的方便性)

d：设计模式上(反转控制的一种应用，类似监听者模式)


----------


> * Java中有内存泄露吗？举一些例子？JNI中呢

1.查询数据库没有关闭游标
2. 构造Adapter时，没有使用缓存的 convertView
3. Bitmap对象不再使用时调用recycle()释放内存
4. 无用时没有释放对象的引用
5. 在Activity中使用非静态的内部类，并开启一个长时间运行的线程，因为内部类持有Activity的引用，会导致Activity本来可以被gc时却长期得不到回收
6.使用Handler处理消息前，Activity通过例如finish()退出，导致内存泄漏
7.动态注册广播在Activity销毁前没有unregisterReceiver

[Android内存泄漏研究](http://jiajixin.cn/2015/01/06/memory_leak/)

 


----------


> * 请介绍下Android中常用的五种布局

我常用的：`linearlayout`,` RelativeLayout`,` FrameLayout`，`TableLayout`很少用到,`GridLayout`用过一次。


----------

> * 请介绍下Android的数据存储方式

google官方的数据存储方式的定义共有五种：

 - sharedPreference
 - 内存存储
 - 外部存储(其实就是文件存储)
 - SQlite
 - 网络存储

[官方链接](http://developer.android.com/guide/topics/data/data-storage.html)


----------

> * Service的onCreate回调在UI线程中吗

Service生命周期的各个回调和其他的应用组件一样，是跑在主线程中，会影响到你的UI操作或者阻塞主线程中的其他事情


----------


> * 请介绍下ContentProvider是如何实现数据共享的

当一个应用程序需要把自己的数据暴露给其他程序使用时，该就用程序就可通过提供ContentProvider来实现；其他应用程序就可通过`ContentResolver`来操作ContentProvider暴露的数据。
一旦某个应用程序通过ContentProvider暴露了自己的数据操作接口，那么不管该应用程序是否启动，其他应用程序都可以通过该接口来操作该应用程序的内部数据，包括增加数据、删除数据、修改数据、查询数据等。
ContentProvider`以某种Uri的形式对外提供数据`，允许其他应用访问或修改数据；其他应用程序使用ContentResolver根据Uri去访问操作指定数据。
步骤：
1、定义自己的ContentProvider类，该类需要继承Android提供的ContentProvider基类。
2、在AndroidManifest.xml文件中注册个ContentProvider，注册ContenProvider时需要为它绑定一个URL。
例：
android:authorities="com.myit.providers.MyProvider" />
说明：authorities就相当于为该ContentProvider指定URL。
注册后，其他应用程序就可以通过该Uri来访问MyProvider所暴露的数据了。

接下来，使用ContentResolver操作数据，Context提供了如下方法来获取ContentResolver对象。
一般来说，ContentProvider是单例模式，当多个应用程序通过ContentResolver来操作 ContentProvider提供的数据时，ContentResolver调用的数据操作将会委托给同一个ContentProvider处理。
使用ContentResolver操作数据只需两步：
1、调用Activity的ContentResolver获取ContentResolver对象。
2、根据需要调用ContentResolver的insert()、delete()、update()和query（）方法操作数据即可.


----------

> * 请介绍下AsyncTask的内部实现，适用的场景是

[ Android AsyncTask完全解析，带你从源码的角度彻底理解 ](http://blog.csdn.net/guolin_blog/article/details/11711405)

AsyncTask内部也是Handler机制来完成的，只不过Android提供了执行框架来提供线程池来执行相应地任务，因为线程池的大小问题，所以AsyncTask只应该用来执行耗时时间较短的任务，比如HTTP请求，大规模的下载和数据库的更改不适用于AsyncTask，因为会导致线程池堵塞，没有线程来执行其他的任务，导致的情形是会发生AsyncTask根本执行不了的问题。


----------


> * 谈谈你对binder机制的理解

[Android进程间通信（IPC）机制Binder简要介绍和学习计划 ](http://blog.csdn.net/luoshengyang/article/details/6618363)
[bind service](http://chenfuduo.me/2015/07/13/bind-service/)

binder是一种IPC机制,进程间通讯的一种工具.

Java层可以利用aidl工具来实现相应的接口. 


----------


> * Android中进程间通信有哪些实现方式？原理是什么

Intent，Binder（AIDL），Messenger，BroadcastReceiver


----------

> * 介绍下实现一个自定义view的基本流程

1.明确需求，确定你想实现的效果
2.确定是使用组合控件的形式还是全新自定义的形式，组合控件即使用多个系统控件来合成一个新控件，你比如titilebar，这种形式相对简单，[参考](http://blog.csdn.net/chdjj/article/details/21193995)
3.如果是完全自定义一个view的话，你首先需要考虑继承哪个类，是View呢，还是ImageView等子类。
4.根据需要去复写View#onDraw、View#onMeasure、View#onLayout方法
5.根据需要去复写dispatchTouchEvent、onTouchEvent方法
6.根据需要为你的自定义view提供自定义属性，即编写attr.xml,然后在代码中通过TypedArray等类获取到自定义属性值
7.需要处理滑动冲突、像素转换等问题

> 另外一个回答

 - 编写attr.xml文件
 - 在layout布局文件中引用，同时引用命名空间
 - 在自定义控件中进行读取（构造方法拿到attr.xml文件值）
 - 覆写onMeasure()方法
 - 覆写onLayout()方法


----------


> * Android中touch事件的传递机制是怎样的? 

事件传递：

> 基础知识

(1) 所有Touch事件都被封装成了MotionEvent对象，包括Touch的位置、时间、历史记录以及第几个手指(多指触摸)等。

(2) 事件类型分为ACTION_DOWN, ACTION_UP, ACTION_MOVE, ACTION_POINTER_DOWN, ACTION_POINTER_UP, ACTION_CANCEL，每个事件都是以ACTION_DOWN开始ACTION_UP结束。

(3) 对事件的处理包括三类，分别为传递——dispatchTouchEvent()函数、拦截——onInterceptTouchEvent()函数、消费——onTouchEvent()函数和OnTouchListener

> 传递流程

(1) 事件从Activity.dispatchTouchEvent()开始传递，只要没有被停止或拦截，从最上层的View(ViewGroup)开始一直往下(子View)传递。子View可以通过onTouchEvent()对事件进行处理。

(2) 事件由父View(ViewGroup)传递给子View，ViewGroup可以通过onInterceptTouchEvent()对事件做拦截，停止其往下传递。

(3) 如果事件从上往下传递过程中一直没有被停止，且最底层子View没有消费事件，事件会反向往上传递，这时父View(ViewGroup)可以进行消费，如果还是没有被消费的话，最后会到Activity的onTouchEvent()函数。

(4) 如果View没有对ACTION_DOWN进行消费，之后的其他事件不会传递过来。

(5) OnTouchListener优先于onTouchEvent()对事件进行消费。
上面的消费即表示相应函数返回值为true。

[PRE_andevcon_mastering-the-android-touch-system](http://wugengxin.cn/download/pdf/android/PRE_andevcon_mastering-the-android-touch-system.pdf)
[ Touch 事件的分发和消费机制](http://www.cnblogs.com/sunzn/archive/2013/05/10/3064129.html)


----------

> * ANR是什么？怎样避免和解决ANR



ANR:Application Not Responding，即应用无响应

ANR一般有三种类型：

1：`KeyDispatchTimeout(5 seconds)` --主要类型

按键或触摸事件在特定时间内无响应

2：`BroadcastTimeout(10 seconds)`

BroadcastReceiver在特定时间内无法处理完成

3：`ServiceTimeout(20 seconds)` --小概率类型

Service在特定的时间内无法处理完成

超时的原因一般有两种：

(1)当前的事件没有机会得到处理（UI线程正在处理前一个事件没有及时完成或者looper被某种原因阻塞住）

(2)当前的事件正在处理，但没有及时完成

UI线程尽量只做跟UI相关的工作，耗时的工作（数据库操作，I/O，连接网络或者其他可能阻碍UI线程的操作）放入单独的线程处理，尽量用Handler来处理UI thread和thread之间的交互。

UI线程主要包括如下：

* Activity:onCreate(), onResume(), onDestroy(), onKeyDown(), onClick()

* AsyncTask: onPreExecute(), onProgressUpdate(), onPostExecute(), onCancel()

* Mainthread handler: handleMessage(), post(runnable r)

查找ANR的方式：
1. 导出/data/data/anr/traces.txt，找出函数和调用过程，分析代码
2. 通过性能LOG人肉查找


----------

> * 值得阅读的android技术文章

[值得阅读的android技术文章](https://github.com/zmywly8866/Worth-Reading-the-Android-technical-articles)


----------

> * Android多线程的实现方式有哪些?它们的优缺点和适用场景是什么

`Thread & AsyncTask`
Thread 可以与Loop 和 Handler 共用建立消息处理队列
AsyncTask 可以作为线程池并行处理多任务


----------

> * Android下解决滑动冲突的常见思路是什么

相关的滑动组件 重写`onInterceptTouchEvent`，然后判断根据xy值，来决定是否要拦截当前操作

[Android Touch事件传递机制](http://www.trinea.cn/android/touch-event-delivery-mechanism/)
[Android 事件分发机制详解](http://stackvoid.com/details-dispatch-onTouch-Event-in-Android/)


----------


> * 如何把一个应用设置为系统应用



成为系统应用，首先要在 对应设备的 Android 源码SDK下编译，编译好之后：

 - 此 Android 设备是 Debug 版本，并且已经 root，直接将此 apk 用 adb 工具 push 到 system/app 或 system/priv-app 下即可。
 - 如果非 root 设备，需要编译后重新烧写设备镜像即可。
 - 有些权限(如 WRITE_SECURE_SETTINGS )，是不开放给第三方应用的，只能在对应设备源码中编译然后作为系统 app 使用。


----------

> * Android注册广播有几种方式? 它们的适用情况是什么?

Android中有两种广播的注册方式：
1、静态注册：AndroidManifest.xml配置文件中；
2、动态注册：Java代码；
静态注册适用于全局广播；动态注册适用于局部广播；

补充一点：有些广播只能通过动态方式注册，比如时间变化事件、屏幕亮灭事件、电量变更事件，因为这些事件触发频率通常很高，如果允许后台监听，会导致进程频繁创建和销毁，从而影响系统整体性能。


----------


> * 你看过Android Framework的代码吗?介绍一下某一个或几个模块? 

我觉得这个问题 最好从app相关系统模块讲一下,例如inputmanager(输入事件),activitymanager,windowmanager等.
或者从类似asyctask,hander,等基础工具来讲.


----------

> * 如何调试Android应用程序

* log
* 断点调试


----------


> * 请用任意语言实现数据结构中的栈

```java
class Stack{
LinkedList list;//声明集合

/**
 * 无参构造方法
 */
public Stack(){
    list=new LinkedList();//创建集合
}

/**
 * 添加方法
 * @param o
 */
public void add(Object o){
    list.push(o);//将元素添加进集合第一个元素 
}

/**
 * 获取方法
 * @return
 */
public Object get(){
    return list.pop();//删除集合的首元素并返回
}

/**
 * 获取集合长度
 * @return
 */
public int size(){
    return list.size();
}

}
```


----------


> * 谈谈开发中遇见的性能优化问题，并说明是如何解决的



根据Google公开课的内容，Android性能问题大致主要以下几大类：

 - UI渲染
 - 代码执行和内存使用
 - 电池

关于如何使用AS的各种工具检测应用性能问题以及如何解决这些问题可以参考下面这些链接：

 - Google在Udacity推出的性能优化进阶课程 - [Udacity825](https://www.udacity.com/course/ud825),当然如果无法观看可以查看优酷上[Android性能专辑](http://v.youku.com/v_show/id_XOTI2NDE1NjAw.html?f=23631701)
 - [胡凯老师总结的Android性能优化典范](http://hukai.me)


----------

> * 谈谈 MVP 模式的优缺点

* [MVP实现Android应用层开发](http://chenfuduo.me/2015/07/13/MVP%E5%AE%9E%E7%8E%B0Android%E5%BA%94%E7%94%A8%E5%B1%82%E5%BC%80%E5%8F%91/)
* [MVC，MVP 和 MVVM ](http://www.ruanyifeng.com/blog/2015/02/mvcmvp_mvvm.html)


----------


> * 本地存储的数据该怎么加密比较好。比如：shared_prefs、sqlite数据、登录用户名、密码等。如果是Aes加密的话，怎么保存key值呢 

密码不要存在本地，一般保存token。最基本的要代码混淆，可以的话加壳，防止反编译。


----------


> * android在线程中创建handler应注意什么




`Looper.prepare()`,主线程使用handler,系统默认prepare了，子线程中创建handler必须在前面`Looper.prepare()`，后面加上`Looper.loop();`

源码中：
主线程：
在程序启动的时候，系统已经帮我们自动调用了Looper.prepare()方法。查看ActivityThread中的main()
```java
public static void main(String[] args) {  
SamplingProfilerIntegration.start();  
CloseGuard.setEnabled(false);  
Environment.initForCurrentUser();  
EventLogger.setReporter(new EventLoggingReporter());  
Process.setArgV0("<pre-initialized>");  
Looper.prepareMainLooper();  
ActivityThread thread = new ActivityThread();  
thread.attach(false);  
if (sMainThreadHandler == null) {  
    sMainThreadHandler = thread.getHandler();  
}  
AsyncTask.init();  
if (false) {  
    Looper.myLooper().setMessageLogging(new LogPrinter(Log.DEBUG, "ActivityThread"));  
}  
Looper.loop();  
throw new RuntimeException("Main thread loop unexpectedly exited");  
}  
```
请注意`Looper.prepareMainLooper()`：
```java
public static final void prepareMainLooper() {  
prepare();  
setMainLooper(myLooper());  
if (Process.supportsProcesses()) {  
    myLooper().mQueue.mQuitAllowed = false;  
}  
}  
```
子线程：
```java
new Thread(new Runnable() {  
        @Override  
        public void run() {  
            Looper.prepare()
            handler2 = new Handler(); 
            Looper.loop() 
        }  
    }).start();
```
如果没有Looper.prepare().会报错：
```xml
Can't create handler inside thread that has not called Looper.prepare()
```
因为没looper对象创建

looper.prepare()源码：
```java
public static final void prepare() {  
if (sThreadLocal.get() != null) {  
    throw new RuntimeException("Only one Looper may be created per thread");  
}  
sThreadLocal.set(new Looper());  
}  
```

> ---------我是优雅的分割线---------

在Android开发中经常会使用到线程，一想到线程，一般都会想到
```java
new Thread(){...}.start();
```
这样的方式。这样如果在一个Activity中多次调用上面的代码，那么将创建多个匿名线程，如果这些线程的没有被销毁，那肯定会影响性能呢。这个时候我么就想到了android提供的一个异步处理线程的类`HandlerThread`。

一般Handler的用法
```java
Handler handler = new Handler(){...};
```
这样创建的handler是在`主线程即UI线程下的Handler`，即`这个Handler是与UI线程下的默认Looper绑定的`（当然也只有主线程才能这么干，子线程是干不了的，除非自己创建个looper）。因此，有些时候会占用ui主线程，引起一些问题，所以我们就想到了重新创建个子线程，来处理handler。。。。
使用HandlerThread解决问题

HandlerThread实际上继承于Thread，只不过它比普通的Thread多了一个Looper。我们可以使用下面的例子创建Handler
```java
HandlerThread thread = new HandlerThread("MyHandlerThread");
thread.start();
```
创建HandlerThread时要把它启动了，即调用start()方法。

接着就是handler的使用，如下：
```java
mHandler = new Handler(thread.getLooper());
//TODO:you can post or send something....
```
创建Handler时将HandlerThread中的looper对象传入。那么这个mHandler对象就是与HandlerThread这个线程绑定了（这时就不再是与UI线程绑定了，这样它处理耗时操作将不会阻塞UI）。


----------

> * Android Webview安全交互

[Android Webview安全交互](http://jiajixin.cn/2014/09/16/webview-js-safety/)


----------


> * Android内存泄露研究

[Android内存泄露研究](http://jiajixin.cn/2015/01/06/memory_leak/)


----------


> * Java程序中，全局变量和局部变量在内存的什么位置？



严谨一点应该这么问：

Java 程序在 JVM 中运行时，全局变量和局部变量在虚拟机的什么位置？

粗略回答：一个是堆一个是栈。


----------


> * Android应用中，如何保证服务常驻内存

[ android service常驻内存的一点思考 ](http://blog.csdn.net/shcalm/article/details/45271449)

首先来看原理

    Android系统中(5.0及以上版本fork子进程也然并卵)当前进程(Process)fork出来的子进程，被系统认为是两个不同的进程。当父进程被杀死的时候，子进程仍然可以存活，并不受影响。

然后来看实现步骤

        用C编写守护进程(即子进程)，守护进程做的事情就是循环检查目标进程是否存在，不存在则启动它。
        在NDK环境中将1中编写的C代码编译打包成可执行文件(BUILD_EXECUTABLE)。
        主进程启动时将守护进程放入私有目录下，赋予可执行权限，启动它即可。

最后是相关代码片段

    主函数包含死循环，调用watch()函数循环检查目标是否存在，不存在则调用restart_target()函数启动它，其中pid参数为目标进程的pid，在Android层可以很简单的获得。
```java
// 监听
while(1)
{
    // 监听
    if (watch(pid)
    {
        // 如果监听不到目标进程，则启动它
        restart_target();
        break;
    }
    // 骚等，歇一会
    sleep(2);
}
```

watch()函数。Linux中所有进程在/proc/目录都会有对应的进程目录，例如对于pid为1234的进程，将存在/proc/1234/目录。检查此目录是否存在即可确定目标进程是否存在。
```C
int watch(char *pidnum)
{
    char proc_path[100];
    DIR *proc_dir;

    // 初始化进程目录
    strcpy(proc_path, "/proc/");
    strcat(proc_path, pidnum);
    strcat(proc_path, "/");
    printf("proccess path is %s\n", proc_path);

    // 尝试访问它以确定是否存在
    proc_dir = opendir(proc_path);

    if (proc_dir == NULL)
    {
        printf("process: %s not exist! start it!\n", pidnum);
        return 1;
    }
    else
    {
        printf("process: %s exist!\n", pidnum);
        return 0;
    }
}
```

 restart_target()函数。使用Android系统的"am startservice"命令去启动目标服务。其他参数的含义请自行Google。
```C
void restart_target()
{
    char cmd_restart[128] = "am startservice --user 0 -a com.a.b.service.YourService";
    popen(cmd_restart, "r");
}
```

以上就是守护进程的主体部分，接下来使用NDK将其编译打包成可执行文件。以下是Android.mk配置文件内容。
```
LOCAL_PATH:= $(call my-dir)

include $(CLEAR_VARS)
LOCAL_SRC_FILES := watchdog.c
LOCAL_MODULE := watchdog
LOCAL_MODULE_PATH := $(TARGET_OUT_EXECUTABLES)
LOCAL_LDLIBS := -llog
include $(BUILD_EXECUTABLE)
```
完成守护进程的编写后，接下来就是使用它。在Android程序运行时将它放到某个可赋予可执行权限的目录，比如私有目录下的files文件夹内。然后调用shell命令赋予它可执行权限并启动它。
```
// 赋予可执行权限
chmod 744 /data/data/com.a.b/files/watchdog

// 执行它，1234为目标要守护的进程pid
/data/data/com.a.b/files/watchdog 1234
```
实际的操作过程中如何保证守护进程的唯一性，就留给大家自己去探索吧。
目前提到的在Android-Service层的尝试都会失败，你再怎么设置，系统的控制权限永远都会比你高，被系统杀死只是时间问题。以上方法可实现守护某进程的目的，进而达到服务常驻后台的效果。


----------

> * Android自定义权限的作用

 - 什么时候使用自定义权限?
 - 和android:exported有什么区别?
 - 为什么很多第三方服务集成，都需要你自己定义权限？比如小米推送，为什么你要加上permission和use-permission两项？

1.自定义权限主要是用来限制对本应用程序或者其他应用程序的特殊组件或功能的访问，如果startActivity()或者startActivityForResult()的调用者没有授予相应权限，那么启动会失败。自定义权限的节点详细信息可以参考官方API Guide Permission，完成权限自定义后可以在<application android:permission>和<activity andriod:permission>、<service andriod:permission>、<receiver andriod:permission>、<provider andriod:permission>分别设置（PS：每个组件的权限设置还有些不一样），表示客户端与应用程序交互的权限许可，如果<activity>没有设置权限，那么默认权限为<application>中的权限，如果两个都没有设置那么该Activity不会被权限保护。总结一下，自定义权限主要还是保护某些组件和功能的可访问性。

2.首先说一下android:exported = [true | false]的功能主要是该组件是否可以被其他应用程序启动或者交互，既然是组件的属性那么就可以分别应用到<activity>、<service>、<receiver>、<provider>,更详细说明可以参考API Guide App Manifeset，当然官方最后说了要完成保护组件也可以使用自定义权限。

3.不加权限就无法访问或者调用对应组件。


----------


> * 如何缩减APK包大小

代码

    保持良好的编程习惯，不要重复或者不用的代码，谨慎添加libs，移除使用不到的libs。
    使用proguard混淆代码，它会对不用的代码做优化，并且混淆后也能够减少安装包的大小。
    native code的部分，大多数情况下只需要支持armabi与x86的架构即可。如果非必须，可以考虑拿掉x86的部分。

资源

    使用Lint工具查找没有使用到的资源。去除不使用的图片，String，XML等等。
    assets目录下的资源请确保没有用不上的文件。
    生成APK的时候，aapt工具本身会对png做优化，但是在此之前还可以使用其他工具如tinypng对图片进行进一步的压缩预处理。
    jpeg还是png，根据需要做选择，在某些时候jpeg可以减少图片的体积。
    对于9.png的图片，可拉伸区域尽量切小，另外可以通过使用9.png拉伸达到大图效果的时候尽量不要使用整张大图。

策略

    有选择性的提供hdpi，xhdpi，xxhdpi的图片资源。建议优先提供xhdpi的图片，对于mdpi，ldpi与xxxhdpi根据需要提供有差异的部分即可。
    尽可能的重用已有的图片资源。例如对称的图片，只需要提供一张，另外一张图片可以通过代码旋转的方式实现。
    能用代码绘制实现的功能，尽量不要使用大量的图片。例如减少使用多张图片组成animate-list的AnimationDrawable，这种方式提供了多张图片很占空间。



[Android App 性能优化实践](http://stackvoid.com/performance-tuning-on-android/)

[Putting Your APKs on Diet](http://cyrilmottier.com/2014/08/26/putting-your-apks-on-diet/)

[腾讯android课之资源后期优化](http://www.cnblogs.com/xiabi/p/4344045.html)

----------

> * 内存泄露检测有什么好方法？

[使用Android studio分析内存泄露](http://www.jianshu.com/p/c49f778e7acf)



检测：
1、DDMS Heap发现内存泄露
dataObject totalSize的大小，是否稳定在一个范围内，如果操作程序，不断增加，说明内存泄露
2、使用Heap Tool进行内存快照前后对比
BlankActivity手动触发GC进行前后对比，对象是否被及时回收

定位：
1、MAT插件打开.hprof具体定位内存泄露：
查看histogram项，选中某一个对象，查看它的GC引用链，因为存在GC引用链的，说明无法回收
2、AndroidStudio的Allocation Tracker：
观测到期间的内存分配，哪些对象被创建，什么时候创建，从而准确定位


----------

> * Android开发中XML解析方式的比较 ，及优缺点



DOM,SAX,Pull解析。

SAX解析器的优点是解析速度快，占用内存少；

DOM在内存中以树形结构存放，因此检索和更新效率会更高。但是对于特别大的文档，解析和加载整个文档将会很耗资源，不适合移动端；

PULL解析器的运行方式和SAX类似，都是基于事件的模式，PULL解析器小巧轻便，解析速度快，简单易用，非常适合在Android移动设备中使用，Android系统内部在解析各种XML时也是用PULL解析器。


----------

> * android内存优化总结

[android内存优化总结](http://www.jianshu.com/p/d9ba8573a940)


----------


> * HttpURLConnection和HttpClient他们各自的优缺点是什么

HttpUrlConnection 在 2.3 以前的版本是有 bug 的，所以之前的版本推荐使用 HttpClient，但是 google 现在已经不维护 HttpClient 了，5.1里面已经把 HttpClient 标过期。另外 HttpURLConnection 支持gzip压缩等，推荐首选它。


----------


> * 谈谈你在工作中是怎样解决一个bug的

思路大体和上面差不多，
1. 异常附近多打印log信息；
2. 分析log日志，实在不行的话进行断点调试；
3. 调试不出结果，上Stack Overflow贴上异常信息，请教大牛(我是不会说百度的，^_^)
4. 再多看看代码，或者从源代码中查找相关信息
5. 实在不行就GG了，找师傅来解决！
以上


----------


> * 在Handler机制如果MessageQueue队列为空，loop()方法中死循环while(true){...}是否会退出，为什么

如果MessageQueue为空，取消息时就阻塞了，不会继续执行，直到队列中有消息。

[Android异步消息处理机制完全解析，带你从源码的角度彻底理解](http://blog.csdn.net/guolin_blog/article/details/9991569)


----------


> * 好的编程习惯


[Android 开发最佳实践](https://github.com/futurice/android-best-practices/blob/master/translations/Chinese/README.cn.md)


----------


> * BroadCastReceiver的安全性，如何解决


[ Android 之使用LocalBroadcastManager解决BroadcastReceiver安全问题 ](http://blog.csdn.net/t12x3456/article/details/9256609)
[ 关于BroadCastReceiver安全性的思考 ](http://blog.csdn.net/yuanzeyao/article/details/38948863)


----------


> * 如何在不失真的条件下显示一张超高清的图片或者长图

针对这个问题，我自己一般用以下两种方法解决：
1、使用WebView来加载该图片；
2、使用MapView或者TileView来显示图片（类似地图的机制）；


[subsampling-scale-image-view
](https://github.com/davemorrissey/subsampling-scale-image-view)


----------

> * 声明ViewHolder内部类时，为什么建议使用static关键字

这个是考静态内部类和非静态内部类的主要区别之一。非静态内部类会隐式持有外部类的引用，就像大家经常将自定义的adapter在Activity类里，然后在adapter类里面是可以随意调用外部activity的方法的。当你将内部类定义为static时，你就调用不了外部类的实例方法了，因为这时候静态内部类是不持有外部类的引用的。声明ViewHolder静态内部类，可以将ViewHolder和外部类解引用。大家会说一般ViewHolder都很简单，不定义为static也没事吧。确实如此，但是如果你将它定义为static的，说明你懂这些含义。万一有一天你在这个ViewHolder加入一些复杂逻辑，做了一些耗时工作，那么如果ViewHolder是非静态内部类的话，就很容易出现内存泄露。如果是静态的话，你就不能直接引用外部类，迫使你关注如何避免相互引用。 所以将 ViewHolder内部类 定义为静态的，是一种好习惯


----------


> *　Android中有哪些方法实现定时和延时任务？它们的适用场景是什么？


倒计时类

    用CountDownTimer

延迟类

    CountDownTimer，可巧妙的将countDownInterval设成和millisInFuture一样，这样就只会调用一次onTick和一次onFinish
    handler.sendMessageDelayed,可参考CountDownTimer的内部实现，简化一下，个人比较推荐这个
    TimerTask，代码写起来比较乱
    Thread.sleep，感觉这种不太好

定时类

    参照延迟类的，自己计算好要延迟多少时间
    handler.sendMessageAtTime
    AlarmManager，适用于定时比较长远的时间，例如闹铃


----------

> * Android对象被回收问题。

补充下：这个问题主要针对Fragment重叠的问题。


[从Fragment被销毁看replace和add的区别](http://fangjie.info/%E4%BB%8Efragment%E8%A2%AB%E9%94%80%E6%AF%81%E7%9C%8Breplace%E5%92%8Cadd%E7%9A%84%E5%8C%BA%E5%88%AB/)


----------

> * Android系统的启动过程

1，通过打开adb shell 然后执行ps命令，我们可以看到首先执行的是init方法！然后我们找到init.c这个文件,
2，然后走init里面的main方法，在这main方法里面执行mkdir进行创建很多的文件夹，和挂载一些目录，
3，然后回去初始化init.rc这个配置文件！在这个配置文件里面回去启动孵化器这个服务，这个服务会去启动app_process这个文件夹，这个文件夹里面有个app_main.cpp这个文件！
4，然后在app_main.cpp这个c文件里面在main方法里面它会去启动安卓的虚拟机，然后安卓虚拟机会去启动os.zygoteinit这个服务！
5，zygoteinit这是个java代码写的，然后我们找到了main方法，在这个方法里面我们看到他首先设置虚拟机的最小堆内存为5兆，然后走到preloadclasses（）这个方法来加载安卓系统所有的2000多个类通过类加载器加载进来,比如activity,contentx,http,...（其实没有必要一下子全部加载下来，我们可以等用到的时候在加载也可以！）
6，然后又走preloadresources（）这个方法来预加载安卓中定义好的资源比如颜色，图片，系统的id等等。。。都加载了！（其实这也是没必要的！ ）
7，然后又走startSystemServer(),这个方法来加载系统的服务！他会先使用natvieJNI去调用C去初始化界面和声音的服务，这就是我们为什么先听到声音和界面的原因！
8，最后等服务加载完成后也就启动起来了!
简之：
linux启动->init进程启动(加载init.rc配置)->zygote启动->systemServer启动,systemServer会通过init1和init2启动navite世界和java世界。


----------

> * Android应用方法数量超过65K个怎么办

使用Android Studio 的gradle 可以构建MutilDex


----------

> * SQLite有哪些优化手段

[SQLite优化方法](http://www.cnblogs.com/devinzhang/archive/2012/01/16/2323949.html)


----------


> * 谈谈你对StrongReference、WeakReference和SoftReference的认识


    强引用（StrongReference）：就是在代码中普遍存在的，类似Object obj = new Object()这类的引用，只要强引用还存在，GC永远不会回收掉被引用的对象。

    软引用（SoftReference）：用来描述一些还有用但非必须的对象。对于软引用关联着的对象，在系统将要发生内存溢出异常时，将会把这些对象列入回收范围之中进行第二次回收。如果这次回收还没有足够的内存，才会抛出内存溢出异常。在JDK 1.2之后，提供了SoftReference类来实习软引用。

    弱引用（WeakReference）：也是用来描述非必须对象的，但是它的强度比软引用更弱一些，被弱引用关联的对象只能生存到了下一次GC发生之前。当GC工作时，无论当时内存是否足够，都会回收只被弱引用关联的对象。在JDK 1.2之后，提供了WeakReference类来实现弱引用。

    虚引用（PhantomReference）：这个引用po主没有提到，不过也可以顺带了解一下。虚引用也称幽灵引用或者幻影引用，它是最弱的一种引用关系。一个对象是否有虚引用的存在，完全不会对其生存时间构成影响，也无法通过虚引用来取得一个对象实例。为一个对象设置虚引用的唯一目的就是在这个对象被GC回收是收到一个系统通知。在JDK 1.2之后提供了PhantomReference类来实现虚引用。
    
    


----------

> * 常见的GC内存泄露情况？附上解决方案

备注：2.3以后的bitmap应该是不需要手动recycle了，内存已经在java层了。

[android内存优化总结](http://www.jianshu.com/p/d9ba8573a940)

[简析Android的垃圾回收与内存泄露](http://www.jianshu.com/p/8c6cf3d7a98a)
[使用Android studio分析内存泄露](http://www.jianshu.com/p/c49f778e7acf)
[内存管理(3)-Android内存泄露分析](http://www.jianshu.com/p/c59c199ca9fa)


----------


> * 你应用中的网络层是怎么设计的？

[Android网络框架](http://blog.csdn.net/column/details/simple-net.html)

用现成的一些框架 然后根据项目需要自己再封装下，比如说你的交互数据是JSON格式的，你就可以用一个网络请求框架+fastjson ，然后写一些Bean 在Work线程把数据用fastjson 直接解析成对象返回，最后对一些错误统一处理


我用的是 android-async-http.
封装了下常用的方法,get post 上传 下载 ,所有的请求我都是用的同步请求.
具体的用法一般都是和业务逻辑在一起,而我的业务逻辑是用异步去处理的.
关于网络请求结果的缓存,我是单独处理的.并没有放在网络层.


----------


> * 微信朋友圈布局是如何优化的


[facebook新闻页ListView优化](http://blog.aaapei.com/article/2015/02/facebookxin-wen-ye-listviewyou-hua)


(getViewTypeCount和getItemViewType )


----------


> * Hashtable的实现原理

     Hashtable类似HashMap，使用hash表来存储键值对。hash表定义:根据设定的hash函数和处理冲突的方式（开放定址、公共溢出区、链地址、重哈希...）将一组关键字映射到一个有限的连续的地址集上（即bucket数组或桶数组），并以关键字在地址集中的“像”作为记录在表中的存储位置，这种表称为hash表。

    2.hash冲突发生时，通过“链表法”或叫"拉链法"来处理冲突，即通过一个链表存储键值对(Map.Entry)。每个Entry对象都有next指针用于指向下一个具有相同hashcode值的Entry。


----------


> * 谈谈你对Bitmap的理解, 什么时候应该手动调用bitmap.recycle()



Bitmap是android中经常使用的一个类，它代表了一个图片资源。
Bitmap消耗内存很严重，如果不注意优化代码，经常会出现OOM问题，优化方式通常有这么几种：
1. 使用缓存；
2. 压缩图片；
3. 及时回收；

至于什么时候需要手动调用recycle，这就看具体场景了，原则是当我们不再使用Bitmao时，需要回收之。另外，我们需要注意，2.3之前Bitmap对象与像素数据是分开存放的，Bitmap对象存在java Heap中而像素数据存放在Native Memory中，这时很有必要调用recycle回收内存。但是2.3之后，Bitmap对象和像素数据都是存在Heap中，GC可以回收其内存。


----------


> * ViewPager中加载Fragment的优化问题？如何做到微信那样切换界面时的延时加载

除了重写Fragment的`setUserVisibleHint()`方法，还可以手动设置`mViewPager.setOffscreenPageLimit();`

```java


private boolean hasLoadedOnce = false; // your boolean field

@Override
public void setUserVisibleHint(boolean isVisibleToUser) {
    super.setUserVisibleHint(isVisibleToUser);

    if (this.isVisible()) {
        // we check that the fragment is becoming visible
        if (isVisibleToUser && !hasLoadedOnce) {
                //do something
            }
        }
    }
}
```

> * 什么是aar？aar和jar有什么区别

“aar”包是 Android 的类库项目的二进制发行包。

文件扩展名是.aar，maven 项目类型应该也是aar，但文件本身是带有以下各项的 zip 文件：

    /AndroidManifest.xml (mandatory)
    /classes.jar (mandatory)
    /res/ (mandatory)
    /R.txt (mandatory)
    /assets/ (optional)
    /libs/*.jar (optional)
    /jni//*.so (optional)
    /proguard.txt (optional)
    /lint.jar (optional)

这些条目是直接位于 zip 文件根目录的。
其中R.txt 文件是aapt带参数--output-text-symbols的输出结果。

jar打包不能包含资源文件，比如一些drawable文件、xml资源文件之类的,aar可以。


----------

> * AIDL设计体现了那些设计思想

代理模式


----------


> * 你在平时开发中会使用到哪些设计模式，能谈谈这些设计模式的使用场景吗

平时用的比较多有单例模式（在内存中仅实例化一个对象时使用），适配器模式（典型的就是ListView和GridView的适配器），建造者模式（AlertDialog.Builder）

模板模式,我最常用的就是把多个Fragment的相同代码抽象出一个基类，在onCreate， onCreateView把子类需要实现的逻辑抽象出来。

例如：
```java
View view = mInflater.inflate(getLayout(), null);
...
protected abstract int getLayout();
```

----------

> * android fragment和activity的区别

 - 可以理解Fragment是一种特殊的View，负责一个模块或者一个特殊部分的展示。
 - 大部分Fragment是依托于Activity存在的，由Activity的FragmentManager来管理
 - Fragment可以解决多Activity的问题，即将3.0之前的频繁Activity跳转改成一个Activity内Fragment的切换。
 - Fragment可以解决碎片化的问题。
 

最重要的区别Activity是一个Context是打通系统交互的一个壳，Fragment是一个实现ComponentCallbacks和 OnCreateContextMenuListener的Object。必须attach到一个Activity上。


----------


> * android清单文件application节点增加tools:replace=""有什么用



这个是android studio用的，对于Eclipse没有任何用。
android studio的Gradle插件默认会启用Manifest Merger Tool，若Library项目中也定义了与主项目相同的属性（例如默认生成的android:icon和android:theme），则此时会合并失败，并报错。
解决方法：
方法1：
在Manifest.xml的application标签下添加tools:replace="android:icon, android:theme"（多个属性用,隔开，并且记住在manifest根标签上加入xmlns:tools="http://schemas.android.com/tools"，否则会找不到namespace哦）

方法2：
在build.gradle根标签上加上useOldManifestMerger true （懒人方法）


----------

> * 请阐述Handler、Looper、MessageQueue之间的关系以及原理

[Android异步消息处理机制完全解析，带你从源码的角度彻底理解 ](http://blog.csdn.net/guolin_blog/article/details/9991569)


----------

> 以上2015-07-26更新


----------



> * HashMap有哪些考察点

1.1. 减少碰撞
我们知道HashMap的时间复杂度取决于O(N//buckets)，所以为了尽量少挂链表，获取hashCode的算法一定要高效；在JDK8中引入了红黑二叉树，当链表元素达到8的时候，把链表动态转成树，可以把最差时间复杂度从O(N)降到O(logN)

1.2. 选好初始容量
resize需要遍历所有的数组并重新计算Hash，所以初始容量确定了，就可以减少损失。

比如你有1000个数据 x * 0.75 = 1000 ,x = 1333，又HashMap中都是按照2^N排序的，所以应该选择2048作为初始容量。

1.3. 数据结构的选择
当数据非常多，对搜索要求高的情况下，考虑使用树。


[HashMap的实现与优化](http://www.jianshu.com/p/e54047b2b563)
[Java面试各种基础坑](http://www.jianshu.com/p/3d58495157e6)


----------


> * mipmap文件夹和drawable文件夹的区别


    它只是用来放启动图标的
    它的好处就是，你只用放一个mipmap图标，它就会给你各种版本（比如平板，手机）的apk自动生成相应分辨率的图标，以节约空间。


----------


> * 当ListView一直向下滑动时加载了很多图片，这时候如果再向上滑动，怎么处理之前已经加载好的图片？另外，不对加载好的图片处理的话一直向下滑会不会造成OOM

如果你用框架的话，比如Picasso,Glide，就不用管它了......

这些框架会自动回收不可见的View，所以不用担心OOM，我极端的测试过1000张 400x272 的图片，都没有卡。


加载过的图片可以缓存在有缓存容量限制的内存中，如使用LruCache，同时也可以缓存在设置有缓存容量限制sdcard中。取图片时统一先向内存缓存中获取，内存缓存中获取不到则向sdcard缓存中获取，还是获取不到再进行下载或读取，获取成功后放入缓存。以上过程均在线程中进行。
这样在图片不断加载的过程中，始终能占用的内存只有缓存上限大小，超过缓存上限的图片将被释放。

线程的话可以设置线程池，并设置线程池大小和执行策略（如FILO）



[如何去准备Android技术面试](http://www.jianshu.com/p/19afef329f65)


----------


> * 离开应用界面一段较长的时间后再回到应用，易出现崩溃的原因 

[不要在Android的Application对象中缓存数据!](http://zmywly8866.github.io/2014/12/26/android-do-not-store-data-in-the-application-object.html)


----------


> * Android中的HelloWorld程序为何在一运行时就申请了多于10MB的堆上内存



个人意见是在build.prop中分配的默认大小照成的
```
cat build.prop | grep  dalvik 
```
也就是无论你写多简单的程序，系统开始都会分配16m的堆大小。如果你手动GC后，自然又把空闲内存回收了。

以下是魅族4.4的配置
```
dalvik.vm.heapsize=36m
dalvik.vm.heapstartsize=16m
dalvik.vm.heapgrowthlimit=256m
dalvik.vm.heapsize=512m
dalvik.vm.heaptargetutilization=0.75
dalvik.vm.heapminfree=4m
dalvik.vm.heapmaxfree=16m
```


----------


> * ?android:attr 和 ?attr/ 分别代表什么意思 有何区别

?attr表示引用的是当前主题中的资源。
?android:attr/表示引用的是android系统中的一些资源。


----------



> * andorid应用第二次登录实现自动登录

我来说一个实际案例的流程吧。前置条件是`所有用户相关接口都走https`，`非用户相关列表类数据走http`。
1. 第一次登陆getUserInfo里带有一个长效token，该长效token用来判断用户是否登陆和换取短token
2. 把长效token保存到SharedPreferences
3. 接口请求用长效token换取短token，短token服务端可以根据你的接口最后一次请求作为标示，超时时间为一天。
4. 所有接口都用短效token
5. 如果返回短效token失效，执行3再直接当前接口
6. 如果长效token失效（用户换设备或超过两周），提示用户登录。


----------

> * 当一个全屏Activity A进入到带有ActionBar（或ToolBar）的非全屏Activity B时，怎么解决Status Bar闪动的问题？


1. 给Activity在清单文件里设置全屏；
2. 在该Activity执行Finish之前，执行下面语句：
```java
getWindow().setFlags(WindowManager.LayoutParams.FLAG_FORCE_NOT_FULLSCREEN, WindowManager.LayoutParams.FLAG_FORCE_NOT_FULLSCREEN);
```
这样在进入其他Activity就不会有Status Bar闪动的问题。


[Switching-from-Full-Screen-to-Non-Full-Screen-Smoothly-in-Android ](http://chrisrisner.com/Switching-from-Full-Screen-to-Non-Full-Screen-Smoothly-in-Android)


----------


> * 关于增量升级


[ 浅析android应用增量升级 ](http://blog.csdn.net/hmg25/article/details/8100896)


----------


> * Android里面为什么要设计出Bundle而不是直接用Map结构

之前在[博客](http://chenfuduo.me)中写过。

Map里实现了Serializable接口，而在Bundle实现了Parcelable的接口

Bundle 父类 `BaseBundle `内部确实有个 `ArrayMap<String, Object>` 类型的 mMap 成员。
我觉得之所以封装为 Bundle 应该和 Android 特有的 `Parcelable` 序列化方式有关（比 JDK 自带的 Serializable 效率高）。通过源码可以看到内部各种 put 和 get 方法都调用了这个 unparcel 方法。


----------


> * 简述MVC模式以及在你项目中的应用

a.模型（model）对象：是应用程序的主体部分，所有的业务逻辑都应该写在该层。
b.视图（view）对象：是应用程序中负责生成用户界面的部分。也是在整个mvc架构中用户唯一可以看到的一层，接收用户的输入，显示处理结果。
c.控制器（control）对象：是根据用户的输入，控制用户界面数据显示及更新model对象状态的部分

 - View：自定义View或ViewGroup，负责将用户的请求通知Controller，并根据model更新界面；
 - Controller：Activity或者Fragment，接收用户请求并更新model；
 - Model：数据模型，负责数据处理相关的逻辑，封装应用程序状态，响应状态查询，通知View改变，对应Android中的datebase、SharePreference等。


----------


> * Android有什么便捷的方式实现activity变暗的效果

```java
  /**
     * 调整窗口的透明度
     * @param from>=0&&from<=1.0f
     * @param to>=0&&to<=1.0f
     * 
     * */
    private void dimBackground(final float from, final float to) {
        final Window window = getWindow();
        ValueAnimator valueAnimator = ValueAnimator.ofFloat(from, to);
        valueAnimator.setDuration(500);
        valueAnimator.addUpdateListener(new AnimatorUpdateListener() {
            @Override
            public void onAnimationUpdate(ValueAnimator animation) {
                WindowManager.LayoutParams params = window.getAttributes();
                params.alpha = (Float) animation.getAnimatedValue();
                window.setAttributes(params);
            }
        });

        valueAnimator.start();
    }
```


----------


> * Android ndk主要在哪些场景下需要使用？有没有哪些坑？ 请具体讲一下。

应用场景:1.加密 2.音视频解码,图像操作等等 3.安全相关,比如hook注入 4.增量更新 5.游戏开发
[ndk使用的注意事项官方文档都有提到](http://developer.android.com/training/articles/perf-jni.html)


----------



> *  ViewPager+Fragment取消预加载（延迟加载） 

[ ViewPager+Fragment取消预加载、延迟加载 ](http://blog.csdn.net/myatlantis/article/details/42643733)


----------


> * 介绍一下Android线程间通信有哪几种方式

1. 共享内存（变量）；
2. 文件，数据库；
3. Handler；
4. Java里的wait()，notify()，notifyAll()


----------


> * Android应用中验证码登陆都有哪些实现方案 

验证码应该只有两种获取方式：
从服务器端获取图片，
通过短信服务，将验证码发送给客户端这两种。


> * 谈谈你对 Application 类的理解

[Don't Store Data in the Application Object](http://www.developerphil.com/dont-store-data-in-the-application-object/)

 - 继承自 ContextWrapper，可用于保存应用全局变量，或者通过全局 Context 注册广播等等（生命周期不受 Activity
   等影响）；
 - 实现了 ComponentCallback2 接口，可以在
   onConfigurationChanged（屏幕方向改变等）、onLowMemory/onTrimMemory（内存不足）时调用组件的相关回调；
 - 提供了注册 ActivityLifecycleCallbacks 和 ComponentCallbacks 的 public
   方法，可以用于监控应用内组件的状态（比如实现类似 Umeng 的统计页面停留时长和访问路径等）；


----------


> * 定位项目中，如何选取定位方案，如何平衡耗电与实时位置的精度？

方案1：
考虑到应用中有多处地方需要使用位置请求，在Application类中开始定位，Application持有一个全局的公共位置对象，然后隔一定时间自动刷新位置，每次刷新成功都把新的位置信息赋值到全局的位置对象，然后每个需要使用位置请求的地方都使用全局的位置信息进行请求。
该方案好处：请求的时候无需再反复定位，每次请求都使用全局的位置对象，节省时间。
该方案弊端：耗电，每隔一定时间自动刷新位置，对电量的消耗比较大。

方案2：按需定位，每次请求前都进行定位。这样做的好处是比较省电，而且节省资源，但是请求时间会变得相对较长。


----------


> * 安卓面试笔试题目

[Android interview questions](http://androidquestions.quora.com/Android-interview-questions)
[Android interview questions for 2-5 yrs experienced](http://androidquestions.quora.com/Android-interview-questions-for-2-5-yrs-experienced)
[阿里2015实习生-客户端笔试题目解析](http://www.jianshu.com/p/027cbf1cb6f6)
[鹅厂2015实习生-客户端笔试题目解析](http://www.jianshu.com/p/b1fcb6c73b28)
[大量Android英文面试题 ](http://skillgun.com/android/interview-questions-and-answers)


----------


> * 求助各位大神，怎么得到手机的唯一标识【注意：不是所有的手机都能得到IMEI及Mac地址】或者其他的折中方式

1. 首先尝试读取IMEI、Mac地址、CPU号等物理信息（有不少工具可以修改IMEI）；
2. 如果均失败，可以自己生成UUID然后保存到文件（文件也可能被篡改或删除）；


[【Android】设备标识](http://www.cnblogs.com/lqminn/p/4204855.html)


----------

> * 在Android的MVP架构中，使用了什么设计模式


    Observer模式：通过EventBus实现订阅者，发布者的功能，实现 Model与 Presenter 的交互。
    Proxy模式：View保持对Presenter的引用，通过Presenter代理，进行交互操作。


----------

> * 自定义View执行invalidate()方法，为什么有时候不会回调onDraw




    自定义一个view时，重写onDraw。
    调用view.invalidate(),会触发onDraw和computeScroll()。前提是该view被附加在当前窗口上
    view.postInvalidate(); //是在非UI线程上调用的

    自定义一个ViewGroup，重写onDraw。
    onDraw可能不会被调用，原因是需要先设置一个背景(颜色或图)。
    表示这个group有东西需要绘制了，才会触发draw，之后是onDraw。
    因此，一般直接重写dispatchDraw来绘制viewGroup

    自定义一个ViewGroup
    dispatchDraw会调用drawChild


----------

> * ContentProvider和sql的区别

ContentProvider的主要还是用于数据共享，其可以对Sqlite，SharePreferences，File等进行数据操作用来共享数据。而sql的可以理解为数据库的一门语言，可以使用它完成CRUD等一系列的操作


----------


> * Android性能测试中都有哪些好的测试工具或者测试方法

内存分析:MAT,DDMS,Leakcanary(Square)
静态分析:Find Bugs,Lint
压力测试:Monkey
自动化测试: UiAutomator,MonkeyRunner,Rubotium,Athrun(淘宝)


----------


> *  防止重复发送网络请求

点击activity上的一个按钮，发送网络请求，在网络比较慢的情况下，用户可能会继续去点击按钮，这个时候，发送其他无谓的请求，不知道大家是怎么处理这类问题来拦截？



    HTTP header中加入max-age，这样某个固定的时间内都将返回empty body，当然这个方法是死的，把时间完全限制了，这个方法回掉也会同样要执行多次。
    还有个晕招，就是直接设置按钮的clickable为false，或者使用progressbar，类似于楼主的方法，比如点赞的场景。
    使用Map的话，在回掉的时候，还是需要回收HashMap的，维护Map还不如只维护一个boolean呢。

Volley中如果开了缓存的话, 相同的请求同时只会有一个去真正的请求, 后续都走缓存, 虽然不会请求多次, 但是回调是会执行多次的, 和这个需求不match


----------

> *如果让你设计一个基于MVC或者MVP设计模式的Android APP架构，你会怎么做


![架构][1]


----------


  [1]: https://cloud.githubusercontent.com/assets/4861905/8716659/e7200e4e-2bc5-11e5-8490-c13d73a82dde.png
