This is for AU
```
adb shell 'pm list packages com.kddi | sed "s/package://" | xargs -r -n1 pm uninstall -k --user 0'
```
