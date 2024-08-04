# FiveGSwitcher

### Download

<a href='https://play.google.com/store/apps/details?id=com.ysy.switcherfiveg&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1'><img alt='Get it on Google Play' src='https://raw.githubusercontent.com/ysy950803/FiveGSwitcher/master-3/google-play-badge.png'/></a>

### Add shortcut switch to MIUI Notification Center

Enter the editing mode of the notification center, and you can find the "5G switch" in the "No switches added" at the bottom. After adding it, long press it to open the detailed settings.

### Support ADB Shell commands

Convenient for running automated scripts on devices with ROOT permissions：[issue#2](https://github.com/ysy950803/FiveGSwitcher/issues/2)

```shell
# true表示开启5G，关闭则为false
am start -n com.ysy.switcherfiveg/.MainActivity --ez enable_5g true
```

### FAQ

**0. Can ROMs from other manufacturers be used?？**

This tool can only be used in MIUI system. Thank you for your support.

**1. It is already MIUI system, but after adding the switch, it is unavailable (gray status)? **

Currently, some models of the new MIUI stable version may have this problem, and the shortcut TileService is killed and restarted by the system (I tried the MIUI development version and native Android, and it won't happen). There is no 100% solution for now. You can try to enable the automatic start permission of this application (generally not recommended), and re-add the shortcut switch to the first page of your notification center (that is, the first position you can see after pulling down), and finally restart the phone.

**2. After clicking the switch, the icon status does not change (no response) or takes a long time to respond? **

The general reason is similar to the first point above. MIUI is likely to have made some magical changes to TileService, and the various callbacks of customized shortcuts are unstable. Currently, the problem is more obvious on the MIUI system based on Android 12, so this application adds a forced switch after long pressing to provide a safety net.
