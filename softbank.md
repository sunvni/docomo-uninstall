# Softbank app remove

```
com.google.android.youtube
jp.co.yahoo.android.yjtop
com.google.ar.lens
com.google.ar.core
com.google.android.apps.youtube.music
jp.softbank.mb.parentalcontrols
jp.softbank.mb.datamigration
jp.softbank.mobileid.prefact
jp.co.softbank.OfficialApp
jp.softbank.mb.dmb
jp.softbank.beginnerguide
jp.softbank.mobileid.installer
jp.softbank.tether.entitlement
jp.softbank.mb.passwordmanager
jp.co.softbank.wispr.froyo
jp.softbank.mb.cbrl
jp.softbank.mb.tdrl
jp.softbank.mb.xcap
jp.softbank.mb.ichinaviclt
jp.co.bbss.android.security.sagiwall_softbank
jp.softbank.meiwakudenwablock
jp.co.sharp.android.emopar
jp.co.sharp.android.emopar.internalcontent2
jp.co.sharp.android.emopar.internalcontent
jp.co.sharp.android.emopa.systemservice
jp.co.sharp.android.emopa.overlayservice
com.android.emergency
jp.co.sharp.android.deblur_viewer
com.facebook.appmanager
com.google.android.videos
com.qualcomm.qti.remoteSimlockAuth
jp.ne.paypay.android.app
jp.co.sharp.android.shaquoscastservice
jp.co.sharp.overlay.android.karadamate.product
jp.co.sharp.overlay.android.lockwallpaperchanger.common
com.dolby.daxappui2
jp.co.sharp.android.scrollauto.common
jp.co.sharp.android.shrobodockservice
com.mcafee.vsm_android_sbm
jp.co.optim.orushrp00
com.amazon.appmanager
com.amazon.avod.thirdpartyclient
jp.co.sharp.android.karadamate
com.adobe.psmobile
jp.co.sharp.android.lockwallpaperchanger
jp.co.sharp.android.migratepicture
jp.co.sharp.android.settingsaquosusefull
jp.co.sharp.android.shlogdservice
sharp.jp.android.makersiteappli
jp.co.sharp.android.restoreguide
jp.co.sharp.android.locationinfoquoter2
jp.co.sharp.android.kittingservice
jp.unext.dolby.experience
com.mobisystems.office
com.google.android.apps.magazines
com.google.android.apps.subscriptions.red
com.google.android.apps.podcasts
jp.softbank.mb.plusmessage
com.google.android.apps.tachyon
jp.co.sharp.android.smarthomehub
jp.co.sharp.android.scshocapture2.common
jp.co.sharp.exapps
com.facebook.services
jp.co.sharp.android.friendlink
com.google.android.cellbroadcastreceiver
com.android.cellbroadcastreceiver.overlay.common
jp.co.sharp.android.LockWeatherWidget
jp.co.sharp.android.providers.soundmemo
jp.co.sharp.android.soundmemo
jp.softbank.mb.bizlock
com.mobiroo.xgen
com.google.android.apps.googleassistant
jp.co.sharp.overlay.android.providers.partnerbookmarks.oem
com.google.android.cellbroadcastservice
com.android.hotwordenrollment.xgoogle
com.google.android.marvin.talkback
com.android.hotwordenrollment.okgoogle
jp.co.sharp.android.scshocapture2
jp.co.sharp.android.paytriggerw
jp.co.sharp.android.kittingapp
jp.co.sharp.android.kittingsuw
```
```
#!/bin/bash

# Filename that contains the list of package names
FILENAME="package_list.txt"

# Read the file line by line
while IFS= read -r package; do
  # Trim whitespace from the beginning and end of the line
  package=$(echo "$package" | xargs)
  
  echo $package
  # Check if the line is not empty
  if [[ -n "$package" ]]; then
    # Attempt to uninstall the package for user 0, ignoring errors
    cmdline="adb shell pm uninstall --user 0 \"$package\" || echo \"Failed to uninstall $package, continuing...\""
    echo $cmdline | sh
  fi
done < "$FILENAME"
```
