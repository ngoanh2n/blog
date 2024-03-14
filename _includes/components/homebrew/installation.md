<!-- LOCATION -->
<!-- _includes/components/homebrew/ -->

<!-- INCLUDE -->
<!-- components/homebrew/installation.md -->

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
{% include components/reference.md path="/env/homebrew" %}
{% endif %}


<!-- MAIN CONTENT -->

{: .note-title .text-epsilon } 
> {{ title }}
>
> ```shell
> /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
> ```
