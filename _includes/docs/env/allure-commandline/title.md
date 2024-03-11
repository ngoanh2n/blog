<!-- _includes/docs/env/allure-commandline/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/allure-commandline/title.md -->
<!-- 2. include docs/env/allure-commandline/title.md isHeading=true -->

{% assign stm = "Allure Commandline" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
