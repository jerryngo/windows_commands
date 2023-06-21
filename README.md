# windows_commands
## A. Opening and Managing Files/Folders Commands:
1. Always open command prompt in administrator Mode: 

Right-click the Command Prompt icon, select “Run as administrator.”

runas /user:Administrator cmd



2. Hide zip or rar files inside an image:

copy /b image.extension+folder.zip image.extension



3. Encrypt files in a folder:

attrib +h +s +r foldername

To unhide it, use this command:

attrib -h -s -r foldername



4. Hide a folder from everyone: 

attrib +h +s +r foldername



5. Show all wifi passwords:

First, show the list of WiFi networks:

netsh wlan show profile

Second, show the password:

netsh wlan show profile wifinetwork key=clear | findstr “Key Content”

To see all WiFi networks:

for /f "skip=9 tokens=1,2 delims=:" %i in ('netsh wlan show profiles') do @if "%j" NEQ "" (echo SSID: %j & netsh wlan show profiles %j key=clear | findstr "Key Content") & echo.



6. Save Output of a Command to a File:

  command >> output.txt



7. Create a batch file:

for /F "tokens=2 delims=:" %a in ('netsh wlan show profile') do @(set wifi_pwd= & for /F "tokens=2 delims=: usebackq" %F IN (`netsh wlan show profile %a key^=clear ^| find "Key Content"`) do @(set wifi_pwd=%F) & echo %a : !wifi_pwd!)
