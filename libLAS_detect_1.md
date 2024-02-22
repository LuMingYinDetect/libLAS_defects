Affected Version:
libLAS 1.8.1 0e21a350506d95938f33e90d8bead6e1aea4d090

Vulnerability Description:
The vulnerability is a memory leak bug located at line 346 of the file /libLAS/apps/ts2las.cpp. This vulnerability could potentially be exploited maliciously to cause resource exhaustion and denial of service attacks.

libLAS download address:
https://github.com/libLAS/libLAS.git

Defect details:

1.A variable named hdr is defined on line 339 of the file ts2las.cpp in /libLAS/apps. The new operator is used to allocate a block of dynamic memory for it. When the if condition on line 343 evaluates to true, the program returns on line 346. During this process, the memory area pointed to by the variable hdr is neither used nor freed, resulting in a memory leak defect, as shown in the following diagram:

![image](https://github.com/LuMingYinDetect/libLAS_defects/blob/main/libLAS_1.png)
