### 第二次作业 
 1. 反编译任意app，并截图   
    * 反编译QQ
  * ![反编译QQ](https://github.com/Test-Seven/Yanjiankai/blob/master/20160306/shortscreen/decompilation_qq.png)
 2. aapt的命令查询app所需要的权限，并截图
    * 查询App所涉及的到安全权限
 * ![查询App的权限](https://github.com/Test-Seven/Yanjiankai/blob/master/20160306/shortscreen/aaptcheckpermission1.png)
 3. 找到任意一个apk or ipa，然后去寻找里面的db，并打开，上传截图；
    * 查询数据库截图
   ![查询数据库截图](https://github.com/Test-Seven/Yanjiankai/blob/master/20160306/shortscreen/checkdatabases.png)
 4. 编写3种并不同切入点的Android monkey 的命令，并成功运行，同时说明切入点是什么
   PS：切入点指，命令运行的侧重点，如：点击，滑动等
    * 侧重滑动事件 adb shell monkey -p packagename  --ignore-crashes --ignore-timeouts --throttle 500 --pct-touch 20 --pct-motion 50 --trackball -s 1010 -v -v -v 500
    * 侧重触摸事件 adb shell monkey -p packagename --ignore-crashes --ignore-timeouts --throttle 500 --pct-touch 60 --pct-motion 10 --trackball -s 1010 -v -v -v 500
    * 侧重按键事件 adb shell monkey -p packagename --ignore-crashes --ignore-timeouts --throttle 500 --pct-syskeys  60--pct-touch 20 --pct-motion 20 --trackball -s 1010 -v -v -v 500
    * 停止Monkey进程
adb shell
ps|grep monkey
kill id
 5. 请找出motion和touch对于的源码里的方法，并找出monkey工具实现点击的最基础的方法是什么
    * motionevent
   ![motionevent](https://github.com/Test-Seven/Yanjiankai/blob/master/20160306/shortscreen/MonkeyMotionEvent.png)
    * Monkeyevent
   ![Monkeyevent](https://github.com/Test-Seven/Yanjiankai/blob/master/20160306/shortscreen/MonkeyTouc.png)
    * 注入事实件的方法，点击滑动的基础
   ![addevent](https://github.com/Test-Seven/Yanjiankai/blob/master/20160306/shortscreen/addevent1.png)
   ![addevent](https://github.com/Test-Seven/Yanjiankai/blob/master/20160306/shortscreen/addevent2.png)
