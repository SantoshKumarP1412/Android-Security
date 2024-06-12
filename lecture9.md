Access Control Issues – Part 3

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/6b763420-f08e-4823-871e-fd2c2f6ea430)


Let’s Create a PIN and Access the Private Notes via the Generated PIN.

<img width="196" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/6f7654a8-a798-4254-84a0-5a6cb8c9d7d8">


Our Goal is to access the Private Notes without interacting with the application,

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/71ff14c8-d249-4f96-aa01-a43059ac2152)


2 Files has been logged while creating PIN and Viewing the Private Notes. Analyze the Source code in the JADX.

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/21f720de-42d8-4f69-bc7a-b730cefa7973)



We can see our AccessControl3Activity stores our pin via a SharedPreferences object, which we covered way back when. When we enter the pin saved in shared_prefs, it launches the AccessControl3NotesActivity activity which validates this pin before showing the notes via
a query(NotesProvider.CONTENT_URI) content query. This content provider will dump all of the notes.
We can dump this content provider via the following command in our terminal:
adb shell content query --uri content://jakhar.aseem.diva.provider.notesprovider/notes/
