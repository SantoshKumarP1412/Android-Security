Input Validation Issues- Part 1

We explore the application by entering values in the search EditText field

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/fc9623f3-b470-43f0-bf8c-0296d3206ed4)

We observe the decompiled source code in the JADX.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/4d6e4590-fa72-4ae6-a834-c08498f761ff)

We understand that for this Task an activity called SQLInjectionActivity is used.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/1db01db3-ec49-48c0-b9da-61781cbe3d84)

We enter 1' OR 1=1-- so that the above SQL query becomes

SELECT * FROM sqliuser WHERE user ='1' OR 1=1--'

The WHERE clause condition gets evaluated to FALSE or TRUE which is equivalent to TRUE, hence all the records in the database are displayed in the Toast message.

<img width="240" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/2b0511fa-0b5f-4572-a96e-d2508009a35c">


Input Validation Issues- Part 2

We explore the application by entering values in the URL EditText field.

<img width="184" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/87a0c7bf-2608-49c7-8585-67ec982d8f5b">

We enter a sensitive path like
file:///data/data/jakhar.aseem.diva/shared_prefs/jakhar.aseem.diva_preferences.xml
Which only the application has access to and normal user of the device does not have access to. We observe that the file contents are displayed in the WebView.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/ecde0e6f-f4cd-420d-967d-d3739d6a1381)
