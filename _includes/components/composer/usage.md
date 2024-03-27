<!-- LOCATION -->
<!-- _includes/components/composer/ -->

<!-- INCLUDE -->
<!-- components/composer/usage.md -->

<!-- VARIABLES -->
<!-- referenced:    [true, false], default to false -->


<!-- READ VARIABLES -->
{% assign referenced = include.referenced %}


<!-- ASSIGN CONSTANTS -->
{% assign reference = "/env/composer#usage" %}


<!-- DECIDE TO DISPLAY THE LINK OF THIS COMPONENT -->
{% if referenced == true %}
{% include components/reference.md path=reference %}
{% endif %}


<!-- MAIN CONTENT -->

#### Init project

{: .note-title .text-epsilon } 
> 
> ```shell
> composer init
> ```
>
> {: .note-title .text-epsilon } 
>>
>> ```
>> This command will guide you through creating your composer.json config.
>> 
>> Package name (<vendor>/<name>): ngoanh2n/example
>> Description []: Demo Automation Test in PHP
>> Author [ngoanh2n <ngoanh2n@gmail.com>, n to skip]: 
>> Minimum Stability []: 
>> Minimum Stability []: 
>> Package Type (e.g. library, project, metapackage, composer-plugin) []: 
>> License []: 
>> 
>> Define your dependencies.
>> 
>> Would you like to define your dependencies (require) interactively [yes]? no
>> Would you like to define your dev dependencies (require-dev) interactively [yes]? no
>> Add PSR-4 autoload mapping? Maps namespace "Ngoanh2n\Example" to the entered relative path. [src/, n to skip]: 
>> Do you confirm generation [yes]? yes
>> Composer could not detect the root package (ngoanh2n/example) version, defaulting to '1.0.0'. See https://getcomposer.org/>> root-version
>> Generating autoload files
>> Generated autoload files
>> PSR-4 autoloading configured. Use "namespace Ngoanh2n\Example;" in src/
>> Include the Composer autoloader with: require 'vendor/autoload.php';
>> ```

#### Install dependency

{: .highlight .text-epsilon } 
Visit [https://packagist.org](https://packagist.org){:target="\_blank"} to search desired packages.

{: .note-title .text-epsilon } 
> 
> ```shell
> composer require --dev phpunit/phpunit
> composer require php-webdriver/webdriver
> ```
