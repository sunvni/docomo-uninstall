# adb shell command for uninstall pre-install app of Docomo mobile
1. Download adb: https://developer.android.com/tools/adb
2. Download USB Driver: https://developer.android.com/studio/run/win-usb?hl=vi
3. Connect your device to computer and run this command from adb folder
```sh
adb shell 'pm list packages jp.co.nttdocomo | sed "s/package://" | xargs -r -n1 pm uninstall -k --user 0'
adb shell 'pm list packages com.nttdocomo | sed "s/package://" | xargs -r -n1 pm uninstall -k --user 0'
```
