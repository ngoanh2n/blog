<!-- LOCATION -->
<!-- _includes/docs/env/allure-commandline/ -->

<!-- INCLUDE -->
<!-- docs/env/allure-commandline/installation.md -->

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
> npm install allure-commandline --global
> ```
