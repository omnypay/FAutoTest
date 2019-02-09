# Initialization failure problem how to debug

1. Try to execute the adb shell am force-stop com.tencent.mm command to kill the WeChat process, then enter the page to be tested and try again.

2. If it still fails. H5 page goes to http://localhost:9222/json

   The applet page goes to http://localhost:9223/json

   Check if the connection is successfully established.

   - Successful connection establishment should see information similar to the picture:

     - <img src='https://github.com/Tencent/FAutoTest/blob/master/docs/images/connectSuc.png?raw=true' width='300'/>

3. If the connection is not established successfully, try to establish a connection manually:

   - H5:
     - First execute adb shell ps | grep com.tencent.mm:tools to get the pid of the process.
     - Execute adb forward tcp:9222 localabstract:webview_devtools_remote_%s to perform port mapping. (Replace %s with the pid obtained in the previous step)
     - Go to http://localhost:9222/json to see if the connection is working.
   - Applets:
     - First execute adb shell dumpsys activity top | grep ACTIVITY to get the pid of the process.
     - Execute adb forward tcp:9223 localabstract:webview_devtools_remote_%s to perform port mapping. (Replace %s with the pid obtained in the previous step)
     - Go to http://localhost:9223/json to see if the connection is working.
     - For some models, the applet cannot be connected properly (there is no applet page displayed in **chrome:inspect**), see QA.

4. If the connection can be successfully established manually, you can check the **h5WebSocketDebugUrlFetcher** (establish H5 connection) and **wxWebSocketDebugUrlFetcher** (establish applet connection) to determine whether the connection problem is caused by different model environments. If there are different ways to establish connection between different models, welcome to pr.
