**\[TIPS\] Newbie guide on how to build YouTube ReVanced**

---

I will teach you how to build YouTube app without Ads by Microsoft Windows.

- Non-Root / Android
- Moderate User / Distributor / Learner
- Traditional Method

---

**1. Download and install Java Runtime Environment (JRE) for Windows v17**

There are 3 Java companies.

> **1.1 Oracle**\
> (https://www.oracle.com/java/technologies/downloads/#jdk17-windows)\
> Need to download the full JDK version. Not recommend.
> 
> **1.2 OpenJDK**\
> (https://openjdk.org)\
> Have only source code.
> 
> **1.3 Azul Zulu**\
> (https://www.azul.com/downloads/?version=java-17-lts&os=windows&architecture=x86-64-bit&package=jre)\
> 100% open source. I prefer this one v17.38.21\
> (https://cdn.azul.com/zulu/bin/zulu17.38.21-ca-jre17.0.5-win_x64.msi)

---

**2. Download ReVanced patches and components**

There are 2 main developer branches that make YouTube patches. Both developers use the same filenames which give us a headache.

**2.1 Official ReVanced** (https://github.com/revanced)

> 2.1.1 revanced-cli-2.19.0.jar\
> https://github.com/revanced/revanced-cli/releases/latest
> 
> 2.1.2 revanced-integrations-0.91.0.apk\
> https://github.com/revanced/revanced-integrations/releases/latest
> 
> 2.1.3 revanced-patches-2.151.0.jar\
> https://github.com/revanced/revanced-patches/releases/latest
> 
> 2.1.4 com.mgoogle.android.gms_0.2.24.220220-220220001.apk\
> https://github.com/TeamVanced/VancedMicroG/releases/latest

**2.2 inotia00 ReVanced Extended** (https://github.com/inotia00)

> 2.2.1 revanced-cli-2.18.3.jar\
> https://github.com/inotia00/revanced-cli/releases/latest
> 
> 2.2.2 revanced-integrations-0.87.0.apk\
> https://github.com/inotia00/revanced-integrations/releases/latest
> 
> 2.2.3 revanced-patches-2.147.3.jar\
> https://github.com/inotia00/revanced-patches/releases/latest
> 
> 2.2.4 com.mgoogle.android.gms_0.2.26.224913.apk\
> https://github.com/inotia00/VancedMicroG/releases/latest

Download all components and save them into two separate folders. I rename app-release-unsigned.apk to revanced-integrations-x.xx.x.apk. No idea why they use that static filename instead of versioning. Keep in mind they are very smart guys and often ignore your feedback and bug reports. So be careful when you submit an issue. You have to check their latest patches about supporting the YouTube version. In this example, the latest support YouTube version is 17.49.37.

---

**3. Download YouTube original APK at apkmirror.com**

> https://www.apkmirror.com/apk/google-inc/youtube/youtube-17-49-37-release/

There are 2 minor versions. You have to download the single APK (nodpi) version.

> https://www.apkmirror.com/apk/google-inc/youtube/youtube-17-49-37-release/youtube-17-49-37-2-android-apk-download/

I rename to com.google.android.youtube_17.49.37.apk

---

**4. Ready to build**

Let's start with the "inotia00 ReVanced Extended" branch. The default package name will be **app.rvx.android.youtube**.

    java.exe -jar revanced-cli-2.18.3.jar -m revanced-integrations-0.87.0.apk -b revanced-patches-2.147.3.jar --keystore=revanced.keystore --options=options.toml -c -t %temp%/ReVanced-Cache -a com.google.android.youtube_17.49.37.apk -o app.rvx.android.youtube_17.49.37.apk

Details:

    java.exe					Java Runtime Environment (JRE) for Windows v17.
    -jar revanced-cli-2.18.3.jar 			Latest ReVanced Build Command Line
    -m revanced-integrations-0.87.0.apk		Latest ReVanced Integrations
    -b revanced-patches-2.147.3.jar			Latest Revanced Patches
    --keystore=revanced.keystore			App Signature. Generate at the first time.
    --options=options.toml				Configuration file. Generate at the first time.
    -c -t %temp%/ReVanced-Cache			Cache Directory
    -a com.google.android.youtube_17.49.37.apk	Original YouTube APK
    -o app.rvx.android.youtube_17.49.37.apk		Output ReVanced YouTube APK

---

**5. Build \~20 times and choose the lowest file size.**
```
150,170,922   app.rvx.android.youtube_17.49.37.apk.18
150,228,266   app.rvx.android.youtube_17.49.37.apk.4
150,265,130   app.rvx.android.youtube_17.49.37.apk.19
150,347,050   app.rvx.android.youtube_17.49.37.apk.8
150,408,490   app.rvx.android.youtube_17.49.37.apk.5
150,420,778   app.rvx.android.youtube_17.49.37.apk.17
150,437,162   app.rvx.android.youtube_17.49.37.apk.10
150,441,258   app.rvx.android.youtube_17.49.37.apk.13
150,453,546   app.rvx.android.youtube_17.49.37.apk.9
150,457,642   app.rvx.android.youtube_17.49.37.apk.7
150,461,738   app.rvx.android.youtube_17.49.37.apk.11
150,494,506   app.rvx.android.youtube_17.49.37.apk.15
150,498,660   app.rvx.android.youtube_17.49.37.apk.6
150,527,274   app.rvx.android.youtube_17.49.37.apk.12
150,531,428   app.rvx.android.youtube_17.49.37.apk.1
150,547,754   app.rvx.android.youtube_17.49.37.apk.3
150,560,042   app.rvx.android.youtube_17.49.37.apk.16
150,568,234   app.rvx.android.youtube_17.49.37.apk.2
150,584,618   app.rvx.android.youtube_17.49.37.apk.20
150,838,762   app.rvx.android.youtube_17.49.37.apk.14
```

---

**FAQ**

1. MicroG (com.mgoogle.android.gms_0.2.xx.apk) is a google login patch. You need to install it if you want to login on YouTube ReVanced app.

2. keystore is an app signature file. It will generate at the first time. If you use the same app signature and package name, you can reinstall an app without lost data. So backup this file in a safe place.

3. options.toml is a configuration file. It will generate at the first time. You can omit this parameter if you run cli in the same folder. Developers often change their syntax. I recommend deleting this file when newly released.

4. For the "Official ReVanced" branch, run the command in the same way. But the default package name will be **app.revanced.android.youtube**.\
`java.exe -jar revanced-cli-2.19.0.jar -m revanced-integrations-0.91.0.apk -b revanced-patches-2.151.0.jar --keystore=revanced.keystore --options=options.toml -c -t %temp%/ReVanced-Cache -a com.google.android.youtube_17.49.37.apk -o app.revanced.android.youtube_17.49.37.apk`  

5. Sometimes there is an error while building. Try again. It will be fine.

6. Latest YouTube for Android 6 is v17.34.36. You can build by using the "inotia00 ReVanced Extended" branch.
   - revanced-cli-2.15.2.jar
   - revanced-integrations-0.71.1.apk
   - revanced-patches-2.111.4.jar






