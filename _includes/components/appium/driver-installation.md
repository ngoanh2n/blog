<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/driver-installation.md -->

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
{% include components/reference.md path="/env/appium#driver" %}
{% endif %}


<!-- MAIN CONTENT -->

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
