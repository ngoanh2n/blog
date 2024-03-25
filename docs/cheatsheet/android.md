---
layout: default
nav_order: 3
parent: Cheatsheet
title: Android
---

{% include components/title.md value="Android Cheatsheet" %}
{% include components/toc.md %}

---

## ADB
[`adb`](https://developer.android.com/tools/adb){:target="\_blank"}

{: .note-title .text-epsilon }
> List attached devices
>
>```shell
> adb devices
>```

{: .note-title .text-epsilon }
> Wait for booting device completed
>
>```shell
> adb wait-for-device
>```


## AVD Manager
[`avdmanager`](https://developer.android.com/tools/avdmanager){:target="\_blank"}

{: .note-title .text-epsilon }
> Create AVD
>
>```shell
> SYSTEM_IMAGES="system-images;android-28;google_apis;x86"
> sdkmanager "$SYSTEM_IMAGES"
> echo "no" | avdmanager --verbose create avd -n MyEmulator -k "$SYSTEM_IMAGES"
>```

## Emulator
[`emulator`](https://developer.android.com/studio/run/emulator-commandline){:target="\_blank"}

{: .note-title .text-epsilon }
> List AVD names
>
>```shell
> emulator -list-avds
>```

{: .note-title .text-epsilon }
> Launch AVD
>
>```shell
> emulator -avd {AVD_NAME}
>```
