## Reverse Engineering of Android App

1. APK Tool
   
![image](https://github.com/udayk01/Android-Security/assets/52235763/fd6e2918-9eb9-4e4d-ad7f-350571245e6e)


Decomiplation: Trying to reach to Source Code From Executable File. Here .dex means Dalvik Executable Code Format

```
apktool d .\app-debug.apk -o test
```

![image](https://github.com/udayk01/Android-Security/assets/52235763/a9c96c89-4f11-4362-95d2-b6bb748e349c)

We observe that the testsample directory does not contain the classes.dex and resources.arsc files previously present in the ZIP file. We observe that there is a apktool.yml file created in the directory. We also observe that there is another AndroidManifest.xml in a new directory called original. We also observe that there is a new directory called smali which was decompiled from the classes.dex file present in the original APK ZIP archive.

![image](https://github.com/udayk01/Android-Security/assets/52235763/41099236-96b4-43bf-9fcb-5f0ef94808b8)

![image](https://github.com/udayk01/Android-Security/assets/52235763/44e8c371-2e2a-40c7-a9d7-26d6e082c844)

![image](https://github.com/udayk01/Android-Security/assets/52235763/edf271e7-7c43-420e-b8e9-bbef8b174a8b)

## Now Jadx Tool

jadx is a Dex to Java decompiler. It is a command line and GUI tools for producing Java source code from Android Dex and Apk files

![image](https://github.com/ananthan05/Android-Security/assets/140697378/9ba325fc-b944-4488-bc31-be6db71a708e)

The decompiled JAVA source code is seen in the JADX window.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/2e2c4ac1-bad8-46b9-a87b-488a39142c49)


We can save the decompiled JAVA source code as a Gradle project.
