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
{% assign reference                    = "/env/appium#driver-macos" %}
{% assign command_install_xcuitest     = "appium driver install xcuitest" %}
{% assign command_install_mac2         = "appium driver install mac2" %}
{% assign command_install_uiautomator2 = "appium driver install uiautomator2" %}
{% assign command_doctor_xcuitest      = "appium driver doctor xcuitest" %}
{% assign command_doctor_mac2          = "appium driver doctor mac2" %}
{% assign command_doctor_uiautomator2  = "appium driver doctor uiautomator2" %}
{% assign location_xcuitest            = "/Users/{USER}/.appium/node_modules/appium-xcuitest-driver" %}
{% assign location_mac2                = "/Users/{USER}/.appium/node_modules/appium-mac2-driver" %}
{% assign location_uiautomator2        = "/Users/{USER}/.appium/node_modules/appium-uiautomator2-driver" %}
{% assign link_ecosystem               = "https://appium.io/docs/en/latest/ecosystem/drivers" %}


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
> Suppose I want to setup environment on `macOS` machine for testing `iOS app`, `macOS app` and `Android app`.
> 
> {: .note-title .text-epsilon }
>> 1. iOS app
>> ```shell
>> {{ command_install_xcuitest }}
>> ```
>> 2. macOS app
>> ```shell
>> {{ command_install_mac2 }}
>> ```
>> 3. Android app
>> ```shell
>> {{ command_install_uiautomator2 }}
>> ```
>
> Or refer to the [Appium Ecosystem's Drivers]({{ link_ecosystem }}){:target="\_blank"} for installing appropriate drivers to your testing environment.
>
> <hr>{: .head-hr }
>
> {: .note-title .text-epsilon }
>> 🔲 Validation
>>
>> ```shell
>> appium driver list --installed
>> ```
>
> {: .note-title .text-epsilon }
>> 🔲 Doctor
>>
>> ```shell
>> {{ command_doctor_xcuitest }}
>> {{ command_doctor_mac2 }}
>> {{ command_doctor_uiautomator2 }}
>> ```
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> `{{ location_xcuitest }}`<br>
>> `{{ location_mac2 }}`<br>
>> `{{ location_uiautomator2 }}`<br>
