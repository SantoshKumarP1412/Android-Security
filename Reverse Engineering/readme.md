1.⁠ ⁠APK Tool

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/59c5f6ca-345d-4f52-a630-aa8d1b533a4c)

Decomiplation: Trying to reach to Source Code From Executable File. 
Here .dex means Dalvik Executable Code Format

	⁠apktool d .\sample.apk -o test

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/5b65dc67-cde9-4245-8ead-b8a3d9859ac7)

We observe that the testsample directory does not contain the classes.dex and resources.arsc files
previously present in the ZIP file.
We observe that there is a apktool.yml file created in the directory.
We also observe that there is another AndroidManifest.xml in a new directory called original.
We also observe that there is a new directory called smali which was decompiled from the classes.dex file
present in the original APK ZIP archive.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/7a8071d6-bd99-4a21-a638-b62814149fa9)


![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/1e916c38-448e-4810-9d8e-f9fc511a6ac2)


![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/f2870317-6a60-4206-83c6-2a8935475570)

Now Jadx Tool

jadx is a Dex to Java decompiler. It is a command line and GUI tools for producing Java source code from
Android Dex and Apk files

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/7d7bd303-ba55-48aa-a9d8-cdf3b328d1fb)

The decompiled JAVA source code is seen in the JADX window.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/882abd45-d4a7-4bbd-8b1a-448f3da234b2)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/253d08a4-cc01-4301-8fc1-809525db58e6)

We can save the decompiled JAVA source code as a Gradle project, as shown in the below screenshots.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/60a4cd28-1ebb-47e8-a17e-81850be53c5e)



![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/dbc3bbca-77c2-46d1-bf72-81daa7c7eb6f)
