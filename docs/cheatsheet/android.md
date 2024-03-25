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

##### List attached devices

{: .note-title .text-epsilon }
>
>```shell
> adb devices
>```

##### Wait for booting device completed

{: .note-title .text-epsilon }
>
>```shell
> adb wait-for-device
>```

## AVD Manager
[`avdmanager`](https://developer.android.com/tools/avdmanager){:target="\_blank"}

##### Create AVD

{: .note-title .text-epsilon }
>
>```shell
> SYSTEM_IMAGES="system-images;android-28;google_apis;x86"
> sdkmanager "$SYSTEM_IMAGES"
> echo "no" | avdmanager --verbose create avd -n MyEmulator -k "$SYSTEM_IMAGES"
>```

## Emulator
[`emulator`](https://developer.android.com/studio/run/emulator-commandline){:target="\_blank"}

##### List AVD names

{: .note-title .text-epsilon }
>
>```shell
> emulator -list-avds
>```

##### Launch AVD

{: .note-title .text-epsilon }
>
>```shell
> emulator -avd {AVD_NAME}
>```
