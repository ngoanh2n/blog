<!-- LOCATION -->
<!-- _includes/components/chocolatey/ -->

<!-- INCLUDE -->
<!-- components/chocolatey/installation.md -->

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
{% include components/reference.md path="/env/chocolatey" %}
{% endif %}


<!-- MAIN CONTENT -->

{: .note-title .text-epsilon } 
> {{ title }}
>
> 1. Open `Windows PowerShell` with administrator privileges
> 2. Run below command:<br>
> ```shell
> Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
> ```
