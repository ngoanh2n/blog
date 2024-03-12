<!-- _includes/docs/env/chocolatey/ -->

{: .note-title .text-epsilon } 
> ✅ Installation
>
> 1. Open `Windows PowerShell` with administrator privileges
> 2. Run below command:<br>
> ```shell
> Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
> ```
