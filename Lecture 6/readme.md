OWASP Top 10 Vulnerabilities in Mobile

We will use Diva_beta.apk (Damn Insecure Vulnerable Application) with list of Top 10 Mobile Vulnerabilities.

We install the APK to the emulator by typing the below command.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/1bc7e4dc-35da-4d5b-bb48-68a6df90afd7)

Insecure Logging

We type adb logcat in the terminal window.

```adb logcat | grep -i "credit card" or adb logcat | Select-String "cred"```

We click on the Login Button

We type a number in the EditText field and click on the Check Out button. We observe that An error occurred toast message is shown, and that the logcat has logged the input that was entered.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/63f730ed-100c-4ed6-949f-e640f25f0860)


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/9a901b7a-8c61-46fa-ab37-bbcb5ca4d90b)


We open JADX and open the diva-beta.apk file.

We observe the decompiled source code and open the LogActivity in the JADX



Hardcoding Issues - Part 1
When we decompile the source code in Jadx app then it will show the code which will also show some hardcoded string.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/0656fde2-cd0e-47b5-b217-67e532af8476)

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/958aa9a2-1555-440d-8d63-609b0246f1ee)


We type the hardcoded vendor key in the EditText field.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/5c009dc4-19b9-482f-8f84-894d493fea0d)

If we type some other hardcoded key then it will deny.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/689de3ed-b828-4e5f-826b-510fc567b67b)

Insecure Data Storage - Part 1
We explore the application by entering username and password in the EditText field.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/75775e7b-77bb-436d-bb35-3dca8c067e1a)



We use adb shell to explore the file system used by the application.
Inside the /data/data/jakhar.aseem.diva directory, we notice the databases and shared_prefs directory.
We type cat shared_prefs/jakhar.aseem.diva_preferences.xml to see the username and password that were saved by the application.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/bd04db54-6a57-4b0a-a81c-20995df0c4b4)


We can observe the decompiled source code and open the InsecureDataStorage1Activity in the Jadx app

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/0f3c24e4-2b2b-425c-8c2f-70c5232d9f44)


Insecure Data Storage - Part 2
We explore the application by entering username and password in the EditText field.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/0f136548-38e5-42f6-a214-bd6fca575cce)

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/556b70b3-e47f-4529-8529-f897b717ff9e)


We have to open the ids2 database using the sqlite3 program, and enter select * from myuser; to view the saved username and password.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/a698cf42-e623-4421-8e4b-ea6df940bd72)


We can view the source code of application by jdax

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/49d8d13a-e794-4953-84cc-c67630c505a1)


Insecure Data Storage - Part 3
We explore the application by entering username and password in the EditText field.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/202a84ab-828c-4720-8a26-c2ae3bf6e5c3)


We observe the decompiled source code and open the InsecureDataStorage3Activity in the JADX.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/648a13c1-572a-40b2-b5a5-309693d14d2e)


Insecure Data Storage - Part 4
We explore the application by entering username and password in the EditText field


We observe the decompiled source code and open the InsecureDataStorage4Activity in the JADX.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/b215b695-b4d5-4ddf-aa45-6e1ee52f5391)



As it is located in external storage, In the adb shell, we navigate to cd /sdcard and type the commands: ls -a and cat .uinfo.txt to view the contents of the file.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/db861f92-919f-41f8-aa6f-48cbca647e4a)


