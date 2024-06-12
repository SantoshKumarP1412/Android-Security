Access Control Issues – Part 1

When we open the adb logcat and click on the button, we can find the activity name. Command – logcat | grep -i “APICredActivity”

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/6728c4ef-dfcf-4044-b5d1-8325bd6e3096)


<img width="466" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/43387358-ac95-4a3c-bb51-ca9b3f1b80a4">



So we run the following command:

adb shell am start –n jakhar.aseem.diva/.APICredsActivity

and confirm that when we run the following command with the device on the screen with the button.And it automatically shows the screen with the credentials without restrictions, like we had pressed the button.
