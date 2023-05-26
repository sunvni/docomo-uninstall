# docomo-uninstall

adb shell 'pm list packages jp.co.nttdocomo | sed "s/package://" | xargs -r -n1 pm uninstall -k --user 0'
adb shell 'pm list packages com.nttdocomo | sed "s/package://" | xargs -r -n1 pm uninstall -k --user 0'
