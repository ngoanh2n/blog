<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/inspector-installation.md -->

<!-- VARIABLES -->
<!-- required:      [true, false], default to true -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign required = include.required %}
{% assign referenced = include.referenced %}


<!-- DECIDE TO DISPLAY THE NECESSITY OF THE INSTALLATION -->
{% if required == false %}
    {% assign title = "🔲 Installation" %}
{% else %}
    {% assign title = "✅ Installation" %}
{% endif %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path="/env/appium#inspector" %}
{% endif %}


<!-- MAIN CONTENT -->

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
