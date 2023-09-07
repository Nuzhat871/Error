# Error
Unable to Register Node from VM to Hub using Selenium Grid4

For Hub:   
D:\Wave3\Drivers> java -jar selenium-server-4.12.0.jar hub
21:24:47.586 INFO [LoggingOptions.configureLogEncoding] - Using the system default encoding
21:24:47.591 INFO [OpenTelemetryTracer.createTracer] - Using OpenTelemetry for tracing
21:24:49.254 INFO [BoundZmqEventBus.<init>] - XPUB binding to [binding to tcp://*:4442, advertising as tcp://192.168.1.64:4442], XSUB binding to [binding to tcp://*:4443, advertising as tcp://192.168.1.64:4443]
21:24:49.305 INFO [UnboundZmqEventBus.<init>] - Connecting to tcp://192.168.1.64:4442 and tcp://192.168.1.64:4443
21:24:49.331 INFO [UnboundZmqEventBus.<init>] - Sockets created
21:24:50.343 INFO [UnboundZmqEventBus.<init>] - Event bus ready
21:24:54.564 INFO [Hub.execute] - Started Selenium Hub 4.12.0 (revision 249f2a7d1b*): http://192.168.1.64:4444



For Node:


D:\Wave3\Drivers> java -jar selenium-server-4.12.0.jar node --detect-drivers true --publish-events tcp://192.168.1.64:4442 --subscribe-events tcp://192.168.1.61:4443 --host 136.226.251.16
21:26:48.239 INFO [LoggingOptions.configureLogEncoding] - Using the system default encoding
21:26:48.381 INFO [OpenTelemetryTracer.createTracer] - Using OpenTelemetry for tracing
21:26:54.691 INFO [UnboundZmqEventBus.<init>] - Connecting to tcp://192.168.1.64:4442 and tcp://192.168.1.61:4443
21:26:55.193 INFO [UnboundZmqEventBus.<init>] - Sockets created
21:26:56.199 INFO [UnboundZmqEventBus.<init>] - Event bus ready
21:26:57.100 INFO [NodeServer.createHandlers] - Reporting self as: http://136.226.251.16:5555
21:26:58.759 INFO [NodeOptions.getSessionFactories] - Detected 2 available processors
21:26:58.766 INFO [NodeOptions.discoverDrivers] - Looking for existing drivers on the PATH.
21:26:58.768 INFO [NodeOptions.discoverDrivers] - Add '--selenium-manager true' to the startup command to setup drivers automatically.
21:27:41.057 WARN [SeleniumManager.lambda$runCommand$1] - Exception managing chrome: Unable to discover proper chromedriver version in offline mode
21:27:41.058 INFO [SeleniumManager.lambda$runCommand$1] - Driver path: D:\Wave3\Drivers\chromedriver.exe
21:27:41.060 INFO [SeleniumManager.lambda$runCommand$1] - Browser path: C:\Program Files (x86)\Google\Chrome\Application\chrome.exe
21:27:42.018 WARN [SeleniumManager.lambda$runCommand$1] - Unable to discover proper msedgedriver version in offline mode
21:27:51.910 WARN [SeleniumManager.lambda$runCommand$1] - error sending request for url (https://product-details.mozilla.org/1.0/firefox_versions.json): error trying to connect: tcp connect error: No connection could be made because the target machine actively refused it. (os error 10061)
21:27:53.676 WARN [SeleniumManager.lambda$runCommand$1] - Unable to discover proper IEDriverServer version in offline mode
21:27:54.448 INFO [NodeOptions.report] - Adding Chrome for {"browserName": "chrome","goog:chromeOptions": {"args": ["--remote-allow-origins=*"]},"platformName": "Windows 10"} 2 times
21:27:54.667 INFO [Node.<init>] - Binding additional locator mechanisms: relative
java.lang.reflect.InvocationTargetException
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.base/java.lang.reflect.Method.invoke(Method.java:566)
        at org.openqa.selenium.grid.Bootstrap.runMain(Bootstrap.java:77)
        at org.openqa.selenium.grid.Bootstrap.main(Bootstrap.java:70)
Caused by: org.openqa.selenium.netty.server.ServerBindException: Could not bind to address or port is already in use. Host 136.226.251.16, Port 5555
        at org.openqa.selenium.netty.server.NettyServer.start(NettyServer.java:168)
        at org.openqa.selenium.grid.node.httpd.NodeServer$1.start(NodeServer.java:189)
        at org.openqa.selenium.grid.node.httpd.NodeServer$1.start(NodeServer.java:186)
        at org.openqa.selenium.grid.node.httpd.NodeServer.execute(NodeServer.java:244)
        at org.openqa.selenium.grid.TemplateGridCommand.lambda$configure$4(TemplateGridCommand.java:122)
        at org.openqa.selenium.grid.TemplateGridCommand$$Lambda$42/0000000000000000.run(Unknown Source)
        at org.openqa.selenium.grid.Main.launch(Main.java:83)
        at org.openqa.selenium.grid.Main.go(Main.java:56)
        at org.openqa.selenium.grid.Main.main(Main.java:41)
        ... 6 more
Caused by: java.net.BindException: Cannot assign requested address: bind
        at java.base/sun.nio.ch.Net.bind0(Native Method)
        at java.base/sun.nio.ch.Net.bind(Net.java:455)
        at java.base/sun.nio.ch.Net.bind(Net.java:447)
        at java.base/sun.nio.ch.ServerSocketChannelImpl.bind(ServerSocketChannelImpl.java:227)
        at io.netty.channel.socket.nio.NioServerSocketChannel.doBind(NioServerSocketChannel.java:141)
        at io.netty.channel.AbstractChannel$AbstractUnsafe.bind(AbstractChannel.java:562)
        at io.netty.channel.DefaultChannelPipeline$HeadContext.bind(DefaultChannelPipeline.java:1334)
        at io.netty.channel.AbstractChannelHandlerContext.invokeBind(AbstractChannelHandlerContext.java:600)
        at io.netty.channel.AbstractChannelHandlerContext.bind(AbstractChannelHandlerContext.java:579)
        at io.netty.handler.logging.LoggingHandler.bind(LoggingHandler.java:230)
        at io.netty.channel.AbstractChannelHandlerContext.invokeBind(AbstractChannelHandlerContext.java:602)
        at io.netty.channel.AbstractChannelHandlerContext.bind(AbstractChannelHandlerContext.java:579)
        at io.netty.channel.DefaultChannelPipeline.bind(DefaultChannelPipeline.java:973)
        at io.netty.channel.AbstractChannel.bind(AbstractChannel.java:260)
        at io.netty.bootstrap.AbstractBootstrap$2.run(AbstractBootstrap.java:356)
        at io.netty.util.concurrent.AbstractEventExecutor.runTask(AbstractEventExecutor.java:174)
        at io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java:167)
        at io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:470)
        at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:569)
        at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:997)
        at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
        at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
        at java.base/java.lang.Thread.run(Thread.java:834)
