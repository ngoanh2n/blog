<!-- LOCATION -->
<!-- _includes/docs/env/appium/ -->

<!-- LOCATION -->
<!-- _includes/components/appium/ -->

<!-- INCLUDE -->
<!-- components/appium/plugin-installation.md -->

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
{% include components/reference.md path="/env/appium#plugin" %}
{% endif %}


<!-- MAIN CONTENT -->

{: .note-title .text-epsilon }
> {{ title }}
>
> {: .note-title .text-epsilon }
>> 🔲 Images
>>
>> Plugin for image comparison and finding elements by image.
>> {: .fs-2 }
>> ```shell
>> appium plugin install images
>> ```
>>
>> {: .note-title .text-epsilon }
>>> Usage
>>>
>>> The plugin must be explicitly activated when launching the Appium server.
>>> {: .fs-2 }
>>> ```shell
>>> appium --use-plugins=images
>>> ```
