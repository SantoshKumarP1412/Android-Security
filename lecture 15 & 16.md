Dynamic Analysis Tool –Crylogger
CRYLOGGER detects cryptographic (crypto) misuses in Android apps. A crypto misuse is an invocation to a crypto API that does not respect common security guidelines, such as those suggested by cryptographers or organizations.
CRYLOGGER detects crypto misuses for you automatically, without requiring to analyse a single line of your code.
First, CRYLOGGER runs your Android app on the official Android Emulator.CRYLOGGER runs your app by using Monkey or the user-interface events you send to the emulator.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/28528fb0-1067-4974-a42a-8f859bb106ce)

adb shell monkey -p your.package.name -v 500

For ex, as shown above frameworks and libcore can be changed accordingly to create a new android distribution and to have our emulator a different logging functionality.
Likewise many changing logging functionality of the open source android OS and making it their own Android distributions.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/a82b1cd2-f9b4-4571-9478-ca871bf62dab)


It will make logs and specifies the analysis made upon cryptographic functionalities of the application.

<img width="426" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/1185060b-912b-465d-aef2-b54166bf07e2">


Above is the repositories that contains source codes of the released android versions and by changing the logging functionality of the desired version of android, new distribution is created on our own.


Benefits of Using Crylogger:

Automatic Detection: Crylogger automates the detection of cryptographic misuse, making it easier and faster to identify security issues compared to manual code reviews.
Runtime Analysis: By analysing the app's behaviours at runtime, Crylogger can detect issues that may not be apparent through static analysis alone.
Focused on Cryptography: The tool is specialized for cryptographic API misuse, providing in- depth insights and recommendations specific to cryptographic security.
