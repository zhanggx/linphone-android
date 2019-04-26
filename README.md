Linphone is a free VoIP and video softphone based on the SIP protocol.

clone from
https://github.com/BelledonneCommunications/linphone-android.git

请遵守linphone相关开源发布协议



## Create an APK with a different package name

Before the 4.1 release, there were a lot of files to edit to change the package name.
Now, simply edit the app/build.gradle file and change the value returned by method ```getPackageName()```
The next build will automatically use this value everywhere thanks to ```manifestPlaceholders``` feature of gradle and Android.

You may have already noticed that the app installed by Android Studio has ```org.linphone.debug``` package name.
If you build the app as release, the package name will be ```org.linphone```. 

## Firebase push notifications

Now that Google Cloud Messaging has been deprecated and will be completely removed on April 11th 2019, the only official way of using push notifications is through Firebase.

However to make Firebase push notifications work, the project needs to have a file named app/google-services.json that contains some confidential informations, so you won't find it (it has been added to the .gitignore file).
This means that if you compile this project, you won't have push notification feature working in the app!

To enable them, just add your own ```google-services.json``` in the app folder.

## Translations

We use transifex so the community can translate the strings of the app in their own language.

Note for developpers: here's how to push/pull string resources to/from transifex:
```
tx pull -af
```
to update local translations with latest transifex changes
```
tx push -s -f --no-interactive
```
to push new strings to transifex so they can be translated.

# CONTRIBUTIONS

In order to submit a patch for inclusion in linphone's source code:

1.    First make sure your patch applies to latest git sources before submitting: patches made to old versions can't and won't be merged.
2.    Fill out and send us an email with the link of pullrequest and the [Contributor Agreement](http://www.belledonne-communications.com/downloads/Belledonne_communications_CA.pdf) for your patch to be included in the git tree.

The goal of this agreement to grant us peaceful exercise of our rights on the linphone source code, while not losing your rights on your contribution.
