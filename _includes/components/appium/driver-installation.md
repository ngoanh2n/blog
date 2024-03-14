<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/driver-installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign platform      = include.platform %}
{% assign required      = include.required %}
{% assign referenced    = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign macos_platform                = "macOS" %}
{% assign macos_app_ios                 = "iOS app" %}
{% assign macos_app_macos               = "macOS app" %}
{% assign windows_platform              = "Windows" %}
{% assign windows_app_android           = "Android app" %}
{% assign windows_app_windows           = "Windows app" %}

{% assign command                       = "appium driver install <installation_key>" %}
{% assign macos_command_xcuitest        = "appium driver install xcuitest" %}
{% assign macos_command_mac2            = "appium driver install mac2" %}
{% assign windows_command_uiautomator2  = "appium driver install uiautomator2" %}
{% assign windows_command_windows       = "appium driver install --source=npm appium-windows-driver" %}
{% assign link_ecosystem_driver         = "https://appium.io/docs/en/latest/ecosystem/drivers" %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path="/env/appium#driver" %}
{% endif %}


<!-- MAIN CONTENT -->
{% if platform %}

<!-- macOS -->
{% if platform == "macos" %}
{% assign value_platform = macos_platform %}
{% assign value_app1     = macos_app_ios %}
{% assign value_app2     = macos_app_macos %}
{% assign value_command1 = macos_command_xcuitest %}
{% assign value_command2 = macos_command_mac2 %}

<!-- Windows -->
{% else %}
{% assign value_platform = windows_platform %}
{% assign value_app1     = windows_app_android %}
{% assign value_app2     = windows_app_windows %}
{% assign value_command1 = windows_command_uiautomator2 %}
{% assign value_command2 = windows_command_windows %}
{% endif %}

{: .note-title .text-epsilon }
> {{ title }}
>
> ```shell
> {{ command }}
> ```
> 
> Suppose I want to setup environment on `{{ value_platform }}` machine for testing `{{ value_app1 }}` and `{{ value_app2 }}`.
> 
> {: .note-title .text-epsilon }
>> ✅ {{ value_app1 }}
>>
>> ```shell
>> {{ value_command1 }}
>> ```
> 
> {: .note-title .text-epsilon }
>> ✅ {{ value_app2 }}
>>
>> ```shell
>> {{ value_command2 }}
>> ```
>
> Or refer to the [Appium Ecosystem's Drivers]({{ link_ecosystem_driver }}){:target="\_blank"} for installing appropriate drivers to your testing environment.

<!-- ALL -->
{% else %}
{: .note-title .text-epsilon }
> {{ title }}
>
> ```shell
> {{ command }}
> ```
>
> {: .note-title .text-epsilon }
>> 🔘 {{ macos_platform }}
>> 
>> Suppose I want to setup environment on `{{ macos_platform }}` machine for testing `{{ macos_app_ios }}` and `{{ macos_app_macos }}`.
>> 
>> {: .note-title .text-epsilon }
>>> ✅ {{ macos_app_ios }}
>>>
>>> ```shell
>>> {{ macos_command_xcuitest }}
>>> ```
>> 
>> {: .note-title .text-epsilon }
>>> ✅ {{ macos_app_macos }}
>>>
>>> ```shell
>>> {{ macos_command_mac2 }}
>>> ```
>
> {: .note-title .text-epsilon }
>> 🔘 {{ windows_platform }}
>> 
>> Suppose I want to setup environment on `{{ windows_platform }}` machine for testing `{{ windows_app_android }}` and `{{ windows_app_windows }}`.
>> 
>> {: .note-title .text-epsilon }
>>> ✅ {{ windows_app_android }}
>>>
>>> ```shell
>>> {{ macos_command_xcuitest }}
>>> ```
>> 
>> {: .note-title .text-epsilon }
>>> ✅ {{ windows_app_windows }}
>>>
>>> ```shell
>>> {{ macos_command_mac2 }}
>>> ```
>
> Or refer to the [Appium Ecosystem's Drivers]({{ link_ecosystem_driver }}){:target="\_blank"} for installing appropriate drivers to your testing environment.
{% endif %}
