<!-- LOCATION -->
<!-- _includes/components/xcode/ -->

<!-- INCLUDE -->
<!-- components/xcode/installation.md -->

<!-- VARIABLES -->
<!-- platform:      [macos, windows], default to ALL -->
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
{% include components/reference.md path="/env/xcode" %}
{% endif %}


<!-- MAIN CONTENT -->

{: .note-title .text-epsilon } 
> {{ title }}
>
> TODO
