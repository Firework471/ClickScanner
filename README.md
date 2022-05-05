# ClickScanner 
The DDGTool of the ClickScanner. It is a backward program slicer. It can detect the assignment process of variables or parameters of APIs. Our framework can be easily extended by researchers for targeted and efficient security vetting of modern Android apps.

# Updated for ClickScanner2.0.jar
I have updated the backward slicing tools of the ClickScanner. ClikcScanner2.0.jar can help you to backward slice the parameters in a certain method. But I didn't have time to update the ClickScanner-timer. So you can simply run the ClickScanner2.0.jar with the command below:

```
java -XmsXXXm -XmxXXXm -jar ~\ClikcScanner2.0.jar ~\TestedAppsPath ~\resultsPath\ timeout(ms) ~\androidjarPath the_signature_of_the_menthod-A_you_want_to_analyze where_is_the_the_menthod-A_invoked which_parameter_do_you_want_to_analyze result_Mode
```
# Parameter Description of ClickScanner2.0.jar

**~\\TestedAppsPath**: the path that contains the apps which are going to be tested.

**~\\resultsPath\\**: the path that contains the results.

**timeout**: timeout (ms).

**the_signature_of_the_menthod-A_you_want_to_analyze**: format: "<java.lang.StringBuilder: java.lang.StringBuilder append(int)>" (maybe you should replace the space with \\s like "<java.lang.StringBuilder:\\sjava.lang.StringBuilder\\sappend(int)>") means that you want to analyze the parameters of the method java.lang.StringBuilder append(int).

**where_is_the_the_menthod-A_invoked**: because menthod-A can be invoked in many methods, so we must make sure that where is the the menthod-A invoked. For example: "<com.xx.xx: void d()>" (maybe you should replace the space with \\s like "<com.xx.xx:\\svoid\\sd()>") means that method-A is invoked in the method void d().

**which_parameter_do_you_want_to_analyze**: format: "0,2,3" means that you want to analyze the first, the third and the forth parameters.

**result_Mode**: There are two modes: "W" that makes the result a single .xml file which contains all the information, and "F" that makes the same result format as before.

# Setup
Due to time limitation, we just give the jar package here, its command is as follows:
```
java -XmsXXXm -XmxXXXm -jar ~\ClickScanner-timer.jar ~\ClickScanner.jar ~\TestedAppsPath ~\resultsPath\ timeout(ms) ~\DoneAppsPath ~\androidjarPath
```
# Parameter Description of ClickScanner.jar
TestedAppsPath is the path that contains the apps which are going to be tested. resultsPath is the path that contains the results. Note that resultsPath needs to contain two subfolder: ~\resultsPath\motion and ~\resultsPath\public. DoneAppsPath is the path that contains the apps which have been tested. androidjarPath is the path that contains the android.jar (you could download it by yourself) file.

# Results Description
Currently the DDGTool of the ClickScanner only supports detecting the assignment process of the parameters of "MotionEvent.obtain" method. We will open an API for users in the future to set the DDGTool of the ClickScanner to detect any variable or parameters of any API.

In order to better meet the needs of researchers, we distributed the test results in two folders. In the ~\resultsPath\motion folder, is the DDG rooted from the "MotionEvent.obtain" method. In the ~\resultsPath\public folder, are the subgraphs of DDG. They are classified into different files according to the four types of data in the paper.

# Improved Version in Camera Ready
The parameters of the current jar package are too complicated and we need more time to sort out more user-friendly APIs. And we will open source the code in the camera ready version.

# Citation
If your found ClickScanner useful for your research, please cite the following paper:
```
@inproceedings{10.1145/3460120.3484546,
author = {Zhu, Tong and Meng, Yan and Hu, Haotian and Zhang, Xiaokuan and Xue, Minhui and Zhu, Haojin},
title = {Dissecting Click Fraud Autonomy in the Wild},
year = {2021},
isbn = {9781450384544},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3460120.3484546},
doi = {10.1145/3460120.3484546},
booktitle = {Proceedings of the 2021 ACM SIGSAC Conference on Computer and Communications Security},
pages = {271–286},
numpages = {16},
keywords = {click fraud, variational autoencoders, humanoid attack, static analysis},
location = {Virtual Event, Republic of Korea},
series = {CCS '21}
}
```
