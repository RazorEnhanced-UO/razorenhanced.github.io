#  Install Instructions for RazorEnhanced + CUO 
(from ATHL33T)
  * Install CUO, this step is beyond the scope of this guide [https://github.com/andreakarasho/ClassicUO/releases ]( Download link .md)
  * Install RazorEnhanced in any location, in this demo the location is C:\RazorEnhanced
  * In your Windows search bar, type powershell, and right click the powershell icon to run as administrator.
  * Enter the following text in the powershell window that is now open
 <code>
cd "C:\RazorEnhanced"
Get-ChildItem *.* -Recurse | Unblock-File
</code>
  * Edit the settings.json file in your CUO directory i.e. C:\Program Files (x86)\Electronic Arts\Ultima Online Classic\ClassicUO\settings.json to look like below:
<code>
{ "username": "",
 "password": "",
 "ip": "login.uoforever.com",
 "port": 2599,
 "ultimaonlinedirectory": "C:\\Program Files (x86)\\Electronic Arts\\Ultima Online Classic",
 "clientversion": "7.0.45.0",
 "lastcharactername": "ur toon",
 "cliloc": "Cliloc.enu",
 "lastservernum": 1,
 "fps": 60,
 "window_position": "0,0",
 "window_size": "1920,1017",
 "is_win_maximized": true,
 "profiler": true,
 "saveaccount": false,
 "autologin": false,
 "reconnect": false,
 "reconnect_time": 0,
 "login_music": true,
 "login_music_volume": 70,
 "shard_type": 0,
 "fixed_time_step": true,
 "run_mouse_in_separate_thread": true,
 "encryption": 0,
 "plugins": [ "C:\\RazorEnhanced\\RazorEnhanced.exe" ] 
}
</code>
  * For OSI server you need the encryption option set top 5like below:
<code>
  "encryption": 5,
</code>