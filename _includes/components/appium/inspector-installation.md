<!-- LOCATION -->
<!-- _includes/docs/env/appium/ -->

<!-- INCLUDE -->
<!-- docs/env/appium/inspector-installation.md -->

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
> Appium Inspector is released in two formats:
> 
> {: .note-title .text-epsilon } 
>> 🔘 Desktop application
>>
>> Download the `Appium-Inspector-mac-xxxx.xx.xx.dmg` file.<br>
>> [https://github.com/appium/appium-inspector/releases](https://github.com/appium/appium-inspector/releases){:target="\_blank"}
>
> 
> {: .note-title .text-epsilon } 
>> 🔘 Web application
>>
>> Appium Inspector is hosted by [Appium Pro](https://appiumpro.com/){:target="\_blank"}.
>> You can inspect your app on this site directly.<br>
>> [https://inspector.appiumpro.com/](https://inspector.appiumpro.com/){:target="\_blank"}
