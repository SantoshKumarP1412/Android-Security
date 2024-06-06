Androwarn is a tool designed to help in the analysis of Android applications by generating analysis reports. It detects potential security issues and vulnerabilities in Android APK files. Here are the steps to use Androwarn for Android malware analysis:

Step 1: Install Dependencies
Androwarn requires certain dependencies to be installed. Ensure you have Python installed, and then install the necessary Python packages.

Install Python version 3.7.1

Activate Python Virtual Environemnt 

<img width="899" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/564fbe82-e600-4e3b-a5a0-0e58dc892543">

Step 2: Download Androwarn
Download the Androwarn tool from its official GitHub repository.

	⁠git clone https://github.com/maaaaz/androwarn.git
cd androwarn

Install all required packages from requirement.txt

	⁠pip install requirement.txt

<img width="1427" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/1cc41148-40ce-4819-b9f2-7eb093321dcf">


<img width="508" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/ae3123cc-a40b-43ee-b5ae-b3be496e0240">

Step 3: Manually Install Androguard

<img width="1418" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/2c846ca5-f5ac-4da6-8b01-61531fb97b78">



<img width="1255" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/c5c9c691-fd43-4354-bfc2-2cce6ac354d6">


Step 4: Run Androwarn


	⁠python androwarn.py -i diva-beta.apk -r html -v 3

Execute Androwarn to analyze the APK file. diva-beta.apk with the path to your APK file.

<img width="1262" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/6d8bad95-7b53-48e3-847b-8170671631fd">

Step 5: Review the Output

Androwarn will generate a detailed report based on the analysis of the APK file. This report will highlight various aspects such as potential security issues, suspicious behaviors, and other vulnerabilities.

Step 6: Interpret the Results

Examine the report to understand the potential threats and vulnerabilities present in the APK file. The report will categorize findings and provide insights into what the APK might be doing.
