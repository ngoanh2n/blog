<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/driver-installation-macos.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference               = "/env/appium#driver-macos" %}
{% assign command_xcuitest        = "appium driver install xcuitest" %}
{% assign command_mac2            = "appium driver install mac2" %}
{% assign command_xcuitest_doctor = "appium driver doctor xcuitest" %}
{% assign command_mac2_doctor     = "appium driver doctor mac2" %}
{% assign link_ecosystem          = "https://appium.io/docs/en/latest/ecosystem/drivers" %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path=reference %}
{% endif %}


<!-- MAIN CONTENT -->

{: .note-title .text-epsilon }
> {{ title }}
> 
> Suppose I want to setup environment on `macOS` machine for testing `iOS app` and `macOS app`.
> 
> {: .note-title .text-epsilon }
>> ✅ iOS app
>>
>> ```shell
>> {{ command_xcuitest }}
>> ```
> 
> {: .note-title .text-epsilon }
>> ✅ macOS app
>>
>> ```shell
>> {{ command_mac2 }}
>> ```
>
> Or refer to the [Appium Ecosystem's Drivers]({{ link_ecosystem }}){:target="\_blank"} for installing appropriate drivers to your testing environment.
>
> <hr>{: .head-hr }
>
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> List already installed drivers.
>> ```shell
>> appium driver list --installed
>> ```
>
> {: .note-title .text-epsilon }
>> 🔲 Doctor
>>
>> Attempts to diagnose and fix common Appium configuration issues.
>> ```shell
>> {{ command_xcuitest_doctor }}
>> {{ command_mac2_doctor }}
>> ```
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> ```
>> /Users/{USER}/.appium/node_modules/appium-xcuitest-driver
>> /Users/{USER}/.appium/node_modules/appium-mac2-driver
>> ```
>>
>> {: .warning }
>> Replace `{USER}` by your current username!