# windows_commands
## A. Opening and Managing Files/Folders Commands:
1. Always open command prompt in administrator Mode: 

 Right-click the Command Prompt icon, select **“Run as administrator.”**

**runas /user:Administrator cmd**

2. Hide zip or rar files inside an image:

**copy /b image.extension+folder.zip image.extension**

3. Encrypt files in a folder:

**attrib +h +s +r foldername**

To unhide it, use this command:

**attrib -h -s -r foldername**

4. Hide a folder from everyone: 

**attrib +h +s +r foldername**

5. Show all wifi passwords:

First, show the list of WiFi networks:

**netsh wlan show profile**

Second, show the password:

**netsh wlan show profile wifinetwork key=clear | findstr “Key Content”**

To see all WiFi networks:

**for /f "skip=9 tokens=1,2 delims=:" %i in ('netsh wlan show profiles') do @if "%j" NEQ "" (echo SSID: %j & netsh wlan show profiles %j key=clear | findstr "Key Content") & echo.**

6. Save Output of a Command to a File:

 **command >> output.txt**

7. Create a batch file:

**for /F "tokens=2 delims=:" %a in ('netsh wlan show profile') do @(set wifi_pwd= & for /F "tokens=2 delims=: usebackq" %F IN (`netsh wlan show profile %a key^=clear ^| find "Key Content"`) do @(set wifi_pwd=%F) & echo %a : !wifi_pwd!)**

## B. System Commands:

8. Display detailed system operating and configuration info: 

**systeminfo**

9. Securely Copy files between remote hosts:

**scp file.txt root@serverip:~/file.txt**

10. Open CMD inside a windows directory:

**“CMD” in the search bar**

11. Open Explorer from the windows command prompt: 

**explorer.**

12. Map a regular folder as a mounted drive:

**subst q: c://filelocation**

13. Remove the Mounted Drive:

**subst /d q:**

14. Change the Background and Text color in command prompt:

**color 07 [background:text]**

15. Change the Prompt Text:

**prompt {text}$G**

16. Reset the Prompt Text:

**prompt**

17. Change the Title of command prompt window:

**title {stuff}**

## C. Network Commands Overview: 

18. Curl the Weather: 

**curl wttr.in/location**

19. Curl Shortened Links to Figure Out the Destination:

**curl --head --location “<https://ntck.co/itprotv”> | location**

20. Check the Status of a Website:

**curl -IsL <http://networkchuck.com/> | findstr ^Location**

21. Check Your Public IP Address: 

**curl checkip.amazonaws.com**

22. Generate a QR Code:

**curl qrenco.de/https://networkchuck.coffee**

## D. Social Media and ChatGPT Commands Overview:

23. Check Social Media:

Youtube 

**curl -s https://decapi.me/youtube/latest_video?user=networkchuck**

Twitter

**curl -s https://decapi.me/twitter/latest?name=networkchuck**

24. Define a word:

**curl dict.org/d:contretemps**

25. Use ChatGPT in CMD with Curl:

**curl <https://api.openai.com/v1/chat/completions> -H "Authorization: Bearer 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" -H "Content-Type: application/json" -d "{\\"model\\": \\"gpt-3.5-turbo\\", \\"messages\\": [{\\"role\\": \\"user\\", \\"content\\": \\"Who is NetworkChuck?\\"}]}"**

26. Create a batch file in ChatGPT: 

**“I want you to act as a Windows command terminal. I will type commands and you will reply with what the terminal should show. I want you to only reply with the terminal output inside one unique code block, and nothing else. Do not write explanations. Do not type commands unless I instruct you to do so. When I need to tell you something in English I will do so by putting text inside curly brackets {like this}. My first command is pwd.”**
## E. File and Folder Management Commands Overview:

27. Visit a website:

**start networkchuck.com**

28. Delete Temporary Files to Clear Space:

**del /q /f /s %temp%\\***
**del /s /q C:\\Windows\\temp\***

29. Telnet Telehack.com:

**Opens a Telnet session to the telehack.com server, allowing you to remotely access and interact with a simulated computer system from the 1980’s**

telnet telehack.com**

30. History of Commands: 

**doskey / history**

## F. Windows Terminal Commands Overview:

31. Use Windows Terminal Instead of Command Prompt:

**1. Download and install Windows Terminal from the Microsoft Store or GitHub. 2. Launch Windows Terminal. 3. Click on the down arrow icon at the top of the window, next to the plus sign, and select "Settings". 4. In the "Settings" window, find the "defaultProfile" setting and set its value to the GUID of the terminal you want to use as the default (e.g. PowerShell, Command Prompt, or WSL). 5. Save the settings and close the "Settings" window. 6. To open a new terminal window, press "Ctrl+Shift+T" or click on the plus sign in the tab bar and select the terminal you want to open.**
 

32. Using Windows Terminal, You Can Drag and Drop Files to the Terminal When You Need the File Location:

**1. Open Windows Terminal and navigate to the directory where you want to run the command. 2. Oen File Explorer and locate the file you want to get the location of. 3. Drag and drop the file onto the terminal window, and the full file path will be pasted into the terminal at the current cursor position.**

33. Open Terminal from Any Folder:

**Shift-right-click on the folder and select Terminal**

34. Get help from Terminal: 

**help**

35. Use PowerShell for advanced tasks beyond Command Prompt: 

**PowerShell is a powerful task automation and configuration management framework from Microsoft, consisting of a command-line shell and scripting language. It can perform advanced tasks beyond the capabilities of the Command Prompt.**
