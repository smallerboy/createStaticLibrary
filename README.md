# createStaticLibrary

###创建.a包

环境:Xcode8  
1.创建一个新工程iOS  
<pre>Framework&Library</pre>
2.修改Build Configuration为Release模式  
<pre>若为Debug模式,大包生成的library会存在Debug-phones/phonessimulator</pre>
3.设置Build Active Architecture<pre><code>targer->BuildSetting->Build Active Architecture Only</code>设置为NO(为YES时,编译的.a静态包为当前的设备指令集)</pre>

#####模拟器&真机
<pre>simulator iphone4s~5为i386 5s~6p 为x86_64</pre>
<pre>phone     iphone3gs~4为armv7  5~5c armv7s 5s-6p arm64</pre>

在真机和simulator中分别编译一次,然后在Products目录下面查看
<pre>Release-phones目录下的.a文件</pre>
<pre>Release-phonesimulator目录下的.a文件</pre>
将两个.a文件合并成一个完整的.a文件(真机和模拟器都能运行)

合并命令:<pre><code>lipo -create 真机.a绝对路径 模拟器.a绝对路径 -output 生成的.a文件路径</code></pre>

[参考链接](http://blog.csdn.net/sinat_16714231/article/details/52837436)




