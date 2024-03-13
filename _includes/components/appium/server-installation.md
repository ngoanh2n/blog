<!-- LOCATION -->
<!-- _includes/docs/env/appium/ -->

<!-- INCLUDE -->
<!-- docs/env/appium/installation.md -->

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
> npm install appium --global
> ```
