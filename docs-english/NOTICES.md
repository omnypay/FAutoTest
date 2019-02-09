# Precautions

### 1. Device connection

When multiple devices are connected, you need to pass in the device number first.

H5 page: `h5Driver = H5Driver(deviceId)`

Applet: `wxDriver = WxDriver(deviceId)`

### 2. Initialization and closing framework

Call `initDriver() after entering the H5 page.

Call `initDriver()` on the first screen of the applet before use.

After the test is completed, you need to call the `driver.close()` method to end the frame.

### 3. Environmental consistency

It is best to kill the WeChat background process before starting the H5 page/small program to ensure consistent environment.

When initializing the applet framework, make sure that WeChat only opens this small program; if you have previously opened other small programs, you need to use the `adb shell am force-stop com.tencent.mm` command to kill the WeChat process and then open the applet. carry out testing

### 4. Control lookup

How to find the xpath of the control you want to click: Find the current page by `chrome:inspect`, you can find the xpath of the control you want to click on (the applet is usually the second inspect of the current page)

### 5. Combine with Native page

UiAutomator is already encapsulated inside the framework for native operation: it can be executed by `driver.d`. The executable operation is similar to Java's UiAutomator. For details, see [uiautomator](*https://github.com/ Xiaocong/uiautomator*)
