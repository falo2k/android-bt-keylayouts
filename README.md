android-bt-keylayouts
=====================

I was somewhat annoyed to find that my Nexus 7 did not have a UK keyboard layout for bluetooth keyboards out of the box.  I've created key layout files and key character maps for my keyboard, the Perixx PERIBOARD-804.

## Deploy to device
adb push keylayout /sdcard/keyboard/keylayout
adb push keychars /sdcard/keyboard/keychars

## Run in adb shell
su;
mount -o remount rw /system;
cat /sdcard/keyboard/keylayout/Vendor_04f2_Product_1063.kl > /system/usr/keylayout/Vendor_04f2_Product_1063.kl;
cat /sdcard/keyboard/keychars/Vendor_04f2_Product_1063.kcm > /system/usr/keychars/Vendor_04f2_Product_1063.kcm;
chmod 644 /system/usr/keychars/Vendor_04f2_Product_1063.kcm;
chmod 644 /system/usr/keylayout/Vendor_04f2_Product_1063.kl;
reboot

Voila!