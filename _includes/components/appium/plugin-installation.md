<!-- LOCATION -->
<!-- _includes/docs/env/appium/ -->

<!-- INCLUDE -->
<!-- docs/env/appium/plugin-installation.md -->

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
