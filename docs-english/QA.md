## Q&A

1. During the pip installation process, timeout always appears and the installation fails. 
> - Please set whether to set the proxy. If it is set, please check if the proxy settings are correct. If it still cannot be solved, you can manually download the uninstallable library and then install it locally. 

2. During the pip installation, the command "python setup.py egg_info failed with error code 1" appears. 
> - Install pip install setuptools_scm ; install pip install pytest-runner 

3. The applet framework initialization has been reported error 

> * It is possible to open other applets before opening the applet. Need to kill the WeChat process using the adb shell am force-stop com.tencent.mm command
> * See [Debugging Guide] for details (https://github.com/Tencent/FAutoTest/blob/master/docs/INITERROR.md)

4. The packaged UIAutomator is not working properly and has been reporting prc errors.

> * Due to the mobile environment problem, UIAutomator is not installed properly, execute the command: 
>
> * ```
> adb shell pm uninstall com.github.uiautomator
> adb shell pm uninstall com.github.uiautomator.test
> adb install app-uiautomator.apk
> adb install app-uiautomator-test.apk
> adb push bundle.jar /data/local/tmp/
> adb push uiautomator-stub.jar /data/local/tmp/
> ```
>
> Details can be found in [uiautomator]([*https://github.com/xiaocong/uiautomator/issues/172*](https://github.com/xiaocong/uiautomator/issues/172) )

5. How to proceed with dragging and other operations

> Get coordinates via getElementCoordinateByXpath. Then call the driver.d.drag() UIAutomator method to operate.

6. What if there are multiple cross-domain Iframes in the body?

> Call the getAllContext, getAllIFrameNode, getBodyNode methods to get the required contextId and NodeId by returning the value
> [Iframe Operation Guide] (IFRAME.md)

7. Why some models can't enter debug mode (there is no applet page displayed in **chrome:inspect**)

> The latest version of WeChat will use different browser kernels depending on the model. If you are not using the QQ browser X5 kernel, you will not be able to enter debug mode.
> The WeChat version 6.6.3 can be installed and resolved by WeChat downgrade.
> [6.6.3 version of WeChat download] (assert/weixin663android1260.apk)
> After downgrading WeChat, you need to re-open WeChat debug mode, see [Start WeChat debug mode] (DEBUG.md)
