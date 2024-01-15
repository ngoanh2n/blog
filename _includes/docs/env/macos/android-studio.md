### Android Studio
<hr>{: .head-hr }

> {: .highlight .text-epsilon }
> Android Studio is an IDE developed by Google, built on JetBrains' IntelliJ IDEA software and designed specifically for Android development.
>
>
> {: .note-title .text-epsilon } 
>> ✅ Installation
>>
>> [https://developer.android.com/studio](https://developer.android.com/studio)
>>
>> {: .highlight }
>>> - Open the `android-studio-xxx.dmg` file
>>> - Drag `Android Studio` to `Applications`
>>> - Open `Android Studio` app
>>>
>>> {: .note-title .text-epsilon } 
>>>> `Complete Installation` window
>>>>
>>>> Select `I do not have a previous version of Studio or I do not want to import my settings`
>>
>>
>> {: .note-title .text-epsilon }
>>> ✅ Android Studio Setup Wizard
>>> 
>>> - Missing SDK > Next
>>> - SDK Component Setup > Next
>>> - Verify Settings > Next
>>> - License Agreement > Accept > Finish
>>> - Download Component > Finish
>>> - Downloading Components > Finish
>>
>>
>> {: .note-title .text-epsilon }
>>> 🔲 Download Components
>>>
>>> {: .highlight }
>>> When missing Android SDK Components.<br>
>>> In this case, I use version `34`.
>>>
>>>
>>> {: .note-title .text-epsilon }
>>>> ✅ Prerequisites
>>>>
>>>> Do the following:
>>>> - Open `Android Studio` app
>>>> - Navigate to `Settings` window<br>
>>>>   By navigating: `Projects` > `More Actions` > `SDK Manager`
>>>
>>>
>>> {: .note-title .text-epsilon }
>>>> ✅ `Settings` window
>>>>
>>>> Navigation route: `Languages & Frameworks` > `Android SDK`
>>>>
>>>>
>>>> {: .note-title .text-epsilon }
>>>>> ✅ `SDK Platforms` tab
>>>>>
>>>>> Tick checkboxes in the following:
>>>>> - `Show Package Details`
>>>>> - `Android 34`
>>>>>   - `Android SDK Platform 34`
>>>>>   - `Sources for Android 34`
>>>>
>>>>
>>>> {: .note-title .text-epsilon }
>>>>> ✅ `SDK Tools` tab
>>>>>
>>>>> Tick checkboxes in the following:
>>>>> - `Show Package Details`
>>>>> - `Android SDK Build-Tools 34` > `34`
>>>>> - `Android SDK Platform-Tools`
>>
>>
>> {: .note-title .text-epsilon }
>>> ✅ Set ANDROID_HOME
>>> 
>>> Execute 3 commands in the following, and replace `{USER}` by your current username!
>>> - `$ echo "export ANDROID_HOME=/Users/{USER}/Library/Android/sdk" >> ~/.zshrc`
>>> - `$ echo "export PATH=\$PATH:\$ANDROID_HOME/platform-tools" >> ~/.zshrc`
>>> - `$ echo "export PATH=\$PATH:\$ANDROID_HOME/tools" >> ~/.zshrc`
>>>