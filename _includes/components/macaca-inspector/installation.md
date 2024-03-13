<!-- LOCATION -->
<!-- _includes/docs/env/macaca-inspector/ -->

<!-- INCLUDE -->
<!-- docs/env/macaca-inspector/installation.md -->

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
> npm install app-inspector --global
> ```
