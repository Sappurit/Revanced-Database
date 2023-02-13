
adb devices

-------------------------------------------------------------------------------

adb install -r com.mgoogle.android.gms_0.2.26.224913.apk \
adb install -r app.revanced.android.youtube_17.34.36_arm64-v8a.apk \
adb install -r app.revanced.android.youtube_17.49.37.apk

-------------------------------------------------------------------------------

adb shell pm list packages -3 \

adb uninstall com.mgoogle.android.gms \
adb uninstall app.revanced.android.youtube \

adb shell pm uninstall -k com.mgoogle.android.gms \
adb shell pm uninstall -k app.revanced.android.youtube

-------------------------------------------------------------------------------

Install \
-r: Reinstall an existing app, keeping its data. \
-d: Allow version code downgrade.

Uninstall \
-k: Keep the data and cache directories around after package removal. Same signature only.

-------------------------------------------------------------------------------

adb: failed to finalize session \
Failure [INSTALL_FAILED_USER_RESTRICTED: Install canceled by user]

https://telegra.ph/How-to-install-v15-on-MIUI-02-11#NON-Root-Installation \
Fix Failure [INSTALL_FAILED_USER_RESTRICTED: Install canceled by user] error in MIUI 12.x

WIFI = Off \
Mobile Data = On \
USB debugging = On \
Install via USB = On

-------------------------------------------------------------------------------



