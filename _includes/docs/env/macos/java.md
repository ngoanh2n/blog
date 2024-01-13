### Java
<hr>{: .head-hr }

**LTS:** 8, 11, 17, 21
{: .label .label-green }

> {: .highlight .text-epsilon }
> Java is a class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible.
>
>
> {: .note-title .text-epsilon } 
>> ✅ Installation
>>
>> {: .note-title .text-epsilon } 
>>> 🔘 [Temurin](https://adoptium.net){:target="\_blank"}
>>>
>>> {: .note-title .text-epsilon } 
>>>> ✅ Install Cask
>>>>
>>>> `$ brew tap homebrew/cask-versions`
>>>
>>> {: .note-title .text-epsilon } 
>>>> ✅ Install Specific Verion
>>>>
>>>> `$ brew install --cask temurin17`
>>
>>
>> {: .note-title .text-epsilon } 
>>> 🔘 [Oracle](https://openjdk.org){:target="\_blank"}
>>>
>>> {: .note-title .text-epsilon } 
>>>> ✅ Install Specific Verion
>>>>
>>>> `$ brew install openjdk@17`
>>>
>>> {: .note-title .text-epsilon } 
>>>> ✅ Symlink For Finding JDK
>>>>
>>>> `$ sudo ln -sfn /usr/local/opt/openjdk@17/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk`
>
>
> {: .note-title .text-epsilon }
>> ✅ Set JAVA_HOME
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Use Latest Version
>>>
>>> `$ echo "export JAVA_HOME=\$(/usr/libexec/java_home)" >> ~/.zshrc`
>>
>> {: .note-title .text-epsilon }
>>> 🔘 Use Specific Version
>>>
>>> `$ echo "export JAVA_HOME=\$(/usr/libexec/java_home -v 17)" >> ~/.zshrc`
>
>
> {: .note-title .text-epsilon }
>> 🔲 Check Version
>>
>> `$ java --version`
>
>
> {: .note-title .text-epsilon }
>> 🔲 Switch To Version
>>
>> {: .note-title .text-epsilon }
>>> ✅ Open `.zshrc `file
>>>
>>> `$ nano ~/.zshrc`
>>
>> {: .note-title .text-epsilon }
>>> ✅ Change desired value of `-v` at below row
>>>
>>> `$ export JAVA_HOME=$(/usr/libexec/java_home -v 17)`
>
>
> {: .note-title .text-epsilon }
>> 🔲 Useful Commands
>>
>> {: .note-title .text-epsilon }
>>> 🔲 Show JAVA_HOME
>>>
>>> `$ /usr/libexec/java_home`
>>
>> {: .note-title .text-epsilon }
>>> 🔲 Show All Version Paths
>>>
>>> `$ /usr/libexec/java_home -V`
>>
>> {: .note-title .text-epsilon }
>>> 🔲 Remove All Versions
>>>
>>> `$ sudo rm -fr /Library/Java/JavaVirtualMachines/jdk-{VERSION}.jdk/` <br>
>>> `$ sudo rm -fr /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin` <br>
>>> `$ sudo rm -fr /Library/PreferencePanes/JavaControlPanel.prefPane`
