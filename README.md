# ClickScanner 
The DDGTool of the ClickScanner. It is a backward program slicer. It can detect the assignment process of variables or parameters of APIs. Our framework can be easily extended by researchers for targeted and efficient security vetting of modern Android apps.

# Setup
Due to time limitation, we just give the jar package here, its command is as follows:
```
java -Xms128m -Xmx14336m -jar ~\ClickScanner-timer.jar ~\ClickScanner.jar ~\TestedAppsPath ~\resultsPath\ timieout(ms) ~\DoneAppsPath ~\androidjarPath
```
# Parameter Description
TestedAppsPath is the path that contains the apps which are going to be tested. resultsPath is the path that contains the results. Note that resultsPath needs to contain two subfolder: ~\resultsPath\motion and ~\resultsPath\public. DoneAppsPath is the path that contains the apps which have been tested. androidjarPath is the path that contains the android.jar (you could download it by yourself) file.

# Results Description
Currently the DDGTool of the ClickScanner only supports detecting the assignment process of the parameters of "MotionEvent.obtain" method. We will open an API for users in the future to set the DDGTool of the ClickScanner to detect any variable or parameters of any API.

In order to better meet the needs of researchers, we distributed the test results in two folders. In the ~\resultsPath\motion folder, is the DDG rooted from the "MotionEvent.obtain" method. In the ~\resultsPath\public folder, are the subgraphs of DDG. They are classified into different files according to the four types of data in the paper.

# Improved Version in Camera Ready
The parameters of the current jar package are too complicated and we need more time to sort out more user-friendly APIs. And we will open source the code in the camera ready version.
