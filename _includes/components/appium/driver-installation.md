<!-- LOCATION -->
<!-- _includes/docs/env/appium/ -->

<!-- INCLUDE -->
<!-- docs/env/appium/driver-installation.md -->

<!-- VARIABLE -->
<!-- required: [true, false], default to true -->

{% assign required = include.required %}

<!-- Set title -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}

{: .note-title .text-epsilon }
> {{ title }}
>
> ```shell
> appium driver install <driver_name>
> ```
> 
> {: .highlight .text-epsilon }
>> driver_name: `xcuitest`, `uiautomator2`, `mac2`...<br>
>> Refer to the [link](http://appium.io/docs/en/latest/ecosystem/drivers/){:target="\_blank"} 
>> for installing appropriate drivers to your testing environment. 
