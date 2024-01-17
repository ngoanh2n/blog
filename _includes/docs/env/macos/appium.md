### Appium
<hr>{: .head-hr }

> {: .highlight .text-epsilon }
> Appium is an open-source project and ecosystem of related software, designed to facilitate UI automation of many app platforms, including mobile (iOS, Android, Tizen), browser (Chrome, Firefox, Safari), desktop (macOS, Windows), TV (Roku, tvOS, Android TV, Samsung), and more!.<br>
> [https://appium.io](https://appium.io){:target="\_blank"}<br>
> [https://github.com/appium/appium](https://github.com/appium/appium){:target="\_blank"}
>
>
> {: .note-title .text-epsilon }
>> ✅ Installation
>>
>> `$ npm install appium --global`
>>
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ Validation
>>>
>>> `$ appium --version`
>>
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ Location
>>>
>>> `/Users/{USER}/.appium/`
>
>
> {: .note-title .text-epsilon }
>> ✅ Install Driver
>>
>> 
>> {: .note-title .text-epsilon }
>>> iOS app
>>>
>>> `$ appium driver install xcuitest`
>>
>>
>> {: .note-title .text-epsilon }
>>> Android app
>>>
>>> `$ appium driver install uiautomator2`
>>
>>
>> {: .note-title .text-epsilon }
>>> Desktop app
>>>
>>> `$ appium driver install mac2`
>>
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ Validation
>>>
>>> `$ appium driver list --installed`
>>
>>
>> {: .note-title .text-epsilon }
>>> ℹ️ Location
>>>
>>> - `/Users/{USER}/.appium/node_modules/appium-xcuitest-driver/`
>>> - `/Users/{USER}/.appium/node_modules/appium-uiautomator2-driver/`
>>> - `/Users/{USER}/.appium/node_modules/appium-mac2-driver/`
>
>
> {: .note-title .text-epsilon }
>> ℹ️ Doctor
>>
>> {: .highlight .text-epsilon }
>> Attempts to diagnose and fix common Appium configuration issues.
>> [https://github.com/appium/packages/doctor](https://github.com/appium/appium/tree/master/packages/doctor){:target="\_blank"}
>>
>>
>> {: .note-title .text-epsilon }
>>> iOS app
>>>
>>> `$ appium driver doctor xcuitest`
>>
>>
>> {: .note-title .text-epsilon }
>>> Android app
>>>
>>> `$ appium driver doctor uiautomator2`
>>
>>
>> {: .note-title .text-epsilon }
>>> Desktop app
>>>
>>> `$ appium driver doctor mac2`
