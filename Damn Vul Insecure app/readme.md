Install APK

OWASP Top 10 Vulnerabilities in Mobile


We will use Diva_beta.apk (Damn Insecure Vulnerable Application) with list of Top 10 Mobile Vulnerabilities.

We install the APK to the emulator by typing the below command.

<img width="573" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/bbede4a5-6fd7-4c3c-ba2e-aa6518bdc336">



<img width="736" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/177ecc17-4760-4f5d-bec8-27360cefa995">

Insecure Logging
We type adb logcat in the terminal window.

adb logcat | grep -i "credit card" or adb logcat | Select-String "cred"

We click on the Login Button

We type a number in the EditText field and click on the Check Out button. We observe that An error occurred toast message is shown, and that the logcat has logged the input that was entered.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/20dd6503-53af-4688-a974-e78ecf289e1a)


We open JADX and open the diva-beta.apk file.

We observe the decompiled source code and open the LogActivity in the JADX

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/e65de9a5-1b7a-4260-9bf9-7d60af020a76)

Hardcoding Issues - Part 1
When we decompile the source code in Jadx app then it will show the code which will also show some hardcoded string.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/df0a9bd6-d206-4ee2-a16d-a252dab59264)

We type the hardcoded vendor key in the EditText field.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/eb0331c9-8388-42e5-a91c-09314089a629)

If we type some other hardcoded key then it will deny.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/28dab75f-2d08-45cc-8ad8-2d3976b592bf)

Insecure Data Storage - Part 1
We explore the application by entering username and password in the EditText field.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/e69d1683-7eb0-400b-b1d6-ba4023793981)

We use adb shell to explore the file system used by the application.
Inside the /data/data/jakhar.aseem.diva directory, we notice the databases and shared_prefs directory.
We type cat shared_prefs/jakhar.aseem.diva_preferences.xml to see the username and password that were saved by the application.



Insecure Data Storage - Part 2
We explore the application by entering username and password in the EditText field.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/c81ba17f-0eaa-44f0-acee-bbef32ef2736)


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/a516d263-e9ff-4257-a55e-7b2e221646da)


Insecure Data Storage - Part 3
We explore the application by entering username and password in the EditText field.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/391f15e1-e119-4266-a6fe-e45fcd1d3f88)
