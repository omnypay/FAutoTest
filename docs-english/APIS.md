# APIs

### WeChat H5

* **def clickElementByXpath(self, xpath, visibleItemXpath =None, duration=50,  tapCount=1)**

> **Interface description: ** Click the control that specifies the xpath. When the control is not visible, it will automatically slide until the control is visible, and then click. When the container is empty, the default sliding point is the middle of the whole screen.
>
> **Parameter Description: ** xpath: Click on the xPath of the control
>
> visibleItemXpath: When there is a container, pass in the xPath of any currently visible item in the container, and then slide the target to the position of the visible item.
>
> duration: the interval between two clicks
>
> tapCount: clicks 



* **def textElementByXpath(self, xpath, text)**

> ** Interface Description: **
>
> Get the focus of the input box first, then use the input api of the Chrome debug protocol to enter the text content.
>
> **Parameter Description: ** xpath: xpath of the input box
>
> text: the text to be entered



* **def scrollWindow(self, x, y, xDistance, yDistance, speed=80)**

> ** Interface Description: **
>
> Swipe by coordinates ((0,0) in the upper left corner of the screen, and the downward and right coordinates gradually increase)
>
> **Parameter description: ** x: Starting X point coordinate of sliding
>
> y: the starting point of the sliding point
>
> xDistance: the distance to slide in the X direction
>
> yDistance: the distance to slide in the Y direction
>
> speed: the speed of the slide



* **def getHtml(self, nodeId=1)**

> ** Interface Description: **
>
> Get the Html code for the specified nodeId
>
> **Parameter Description: **
>
> nodeId: the nodeId returned by the getDocument method. When it is 1, the code of the entire body is returned.



- **def closeWindow(self)**

> ** Interface Description: **
>
> Get the nodeId needed in getHtml, you must call this method before calling getHtml 



- **def returnLastPage(self)**

> ** Interface Description: **
>
> Back to previous page 



* **def scrollPickerByXpath(self, xpath)**

> ** Interface Description: **
>
> Swipe to select picker options 
>
> **Parameter Description: **
>
> xpath: the item to select 



* **def getPageHeight(self)**

> ** Interface Description: **
>
> Get the height of the entire page page



* **def getWindowHeight(self)**

> ** Interface Description: **
>
> Get the height of the phone screen 



* **def getWindowWidth(self)**

> ** Interface Description: **
>
> Get the width of the phone screen



* **def getElementTextByXpath(self, xpath)**

> **Interface description: ** Get the text content of the target
>
> **Parameter Description: ** xpath: target xpath



* **def getElementSrcByXpath(self, xpath)**

> **Interface description: ** Get the src content of the target
>
> **Parameter Description: ** xpath: target xpath



* **def getElementClassNameByXpath(self, xpath)**

> **Interface description: ** Get the className of the target
>
> **Parameter Description: ** xpath: target xpath



* **def getCurrentPageUrl(self)**

> **Interface description: ** Current page url



* **def getElementByXpath(self, xpath)**

> **Interface description: ** Return the lxml wrapped element object, you can use lxml syntax to get the object information
>
> **Parameter Description: ** xpath: target xpath
>
> For example: you can use element.get("attrs") to get the data of the property; you can get its text with element.text; when the element contains the list, use the for loop to read each itemml; more The operation method of lxml element can be seen in http://lxml.de/tutorial.html



* **def isElementExist(self, xpath)**

> **Interface description: ** Return a boolean to determine if the element exists
>
> **Parameter Description: ** xpath: target xpath



* **def navigateToPage(self, url)**

> **Interface Description: ** Jump to the specified url, not available on WeChat version 6.5.13 or higher
>
> **Parameter description: ** url: url to jump



* **def executeScript(self, script)**

> **Interface description: ** Manually send js command and execute, return execution result
>
> **Parameter description: ** script: js instruction to be executed



* **def focusElementByXpath(self, xpath)**

> **Interface Description: ** Call the target's focus() method.
>
> **Parameter Description: ** xpath: target xpath



* **def scrollToElementByXpath(self, xpath, visibleItemXpath =None, speed=400)**

> ** Interface Description: **
>
> Sliding the screen so that the control of the specified xpath is visible. The default sliding point is the center of the screen, and the margin is the entire screen. When there is a container, the xpath of any currently visible item in the container is passed, and then the target is slid to visible. Item location
>
> **Parameter Description: ** xpath: xpath to slide to the controls in the screen
>
> visibleItemXpath: the xpath of an item currently visible in the container; the sliding position is the middle of the container



* **def clearInputTextByXpath(self, xpath)**

> **Interface description: ** Clear the text of the input box
>
> **Parameter Description: ** xpath: xpath of input box



* **def getMemoryInfo(self)**

> ** Interface Description: ** Get memory information occupied by H5 process



* **def getCPUInfo(self)**

> ** Interface Description: ** Obtain CPU information occupied by H5 process



* **def setDebugLogMode(self)**

> ** Interface Description: ** log information level adjustment settings, only show info level messages by default
>
> After calling initDriver, you can call this method to set the detailed message showing the debug level.

 

* **getElementCoordinateByXpath(self, elementXpath)**

> **Interface description: ** Get the coordinates of the Element
>
> **Parameter Description: ** param elementXpath: the xpath of the element to get the coordinates
>
> **Return value: ** x, y coordinates of element relative to the entire screen, in px

 

* **def longClickElementByXpath(self,xpath, visibleItemXpath=None, duration=2000, tapCount=1)**

> ** Interface Description: ** Long press, the default time is 2s, the other is the same as 2.2.1

 

* **def repeatedClickElementByXpath(self,xpath, visibleItemXpath=None, duration=50, tapCount=2)**

> ** Interface Description: ** Click multiple times, double click by default, other with 2.2.1

 

* **getIFrameContextId(self)**

> **Interface description: ** Called when there is only one Iframe in the body tag, get the contextId

 

* **def getIFrameNodeId(self)**

> **Interface description: ** Called when there is only one Iframe in the body tag, get nodeId

 

* **def getAllContext(self)**

> **Interface Description: ** Get all the ContextId, domain and FrameId of the current page. When there are multiple cross-domain Iframes in the body, you can get the FrameId of the corresponding Iframe by this method.



* **def getAllIFrameNode(self)**

> **Interface Description:** Get all IFrameNodes in the body tag



* **def getBodyNode(self)**

> ** Interface Description: ** Get the frameId of all nodes in the body



* **def getIFrameElementCoordinateByXpath(self, elementXpath, iFrameXpath, contextId)**

> **Interface description: ** Get the coordinates of the Element
>
> **Parameter Description: ** param elementXpath: the xpath of the element to get the coordinates
>
> iFrameXpath: xpath of outer iFrame
>
> contextId: iFrame的ContextId
>
> **Return value: ** x, y coordinates of element relative to the entire screen, in px



* **def getIFrameHtml(self, nodeId=None)**

> **Interface Description:** Get Html for the specified nodeId page



* **def getIFrameElementByXpath(self, xpath, nodeId)**

> ** Interface Description: ** nodeId is the nodeId of the page where element is located, and the rest is the same as 2.2.16





## Applets

The interface method provided by the applet is similar to that of the H5. For details, refer to the interface of the H5.

* **def returnLastPage(self)**

* **def getPageHeight(self)**

* **def getWindowWidth(self)**

* **def isElementExist(self, xpath)**

* **def getElementTextByXpath(self, xpath)**

* **def getElementSrcByXpath(self, xpath)**

* **def textElementByXpath(self, xpath, text, needClick=False)**

> **Parameter description: ** needClick: If true, the control will be clicked first to get the focus

* **def clickElementByXpath(self, xpath, containerXpath=None，byUiautomator=False)**

> **Parameter Description: ** byUiautomator: When the traditional method can't click, pass byUiautomator to true using Uiautomator to click def getWindowHeight(self):

* **def scrollWindow(self, x, y, xDistance, yDistance, speed=800)**

* **def scrollToElementByXpath(self, xpath, containerXpath=None, speed=400)**
* **def getDocument(self)**

* **def getHtml(self, nodeId=1)**

* **def getElementByXpath(self, xpath)**

* **def getMemoryInfo(self)**

* **def getCPUInfo(self)**

* **def setDebugLogMode(self)**

* **getElementCoordinateByXpath(self, elementXpath)**
