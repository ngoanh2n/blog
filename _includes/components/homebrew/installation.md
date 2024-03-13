<!-- LOCATION -->
<!-- _includes/docs/env/homebrew/ -->

<!-- INCLUDE -->
<!-- docs/env/homebrew/installation.md -->

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
> /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
> ```
