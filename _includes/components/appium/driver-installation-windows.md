<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/driver-installation-windows.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required   = include.required %}
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference                    = "/env/appium#driver-windows" %}
{% assign command_install_uiautomator2 = "appium driver install uiautomator2" %}
{% assign command_install_windows      = "appium driver install --source=npm appium-windows-driver" %}
{% assign command_doctor_uiautomator2  = "appium driver doctor uiautomator2" %}
{% assign command_doctor_windows       = "appium driver doctor windows" %}
{% assign location_uiautomator2        = "C:\Users\{USER}\.appium\node_modules\appium-uiautomator2-driver" %}
{% assign location_windows             = "C:\Users\{USER}\.appium\node_modules\appium-windows-driver" %}
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
> Suppose I want to setup environment on `Windows` machine for testing `Android app` and `Windows app`.
> 
> {: .note-title .text-epsilon }
>> ✅ Android app
>>
>> ```shell
>> {{ command_install_uiautomator2 }}
>> ```
> 
> {: .note-title .text-epsilon }
>> ✅ Windows app
>>
>> ```shell
>> {{ command_install_windows }}
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
>> {{ command_doctor_uiautomator2 }}
>> {{ command_doctor_windows }}
>> ```
>
> {: .note-title .text-epsilon }
>> ℹ️ Location
>>
>> `{{ location_uiautomator2 }}`<br>
>> `{{ location_windows }}`
