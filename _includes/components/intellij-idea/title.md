<!-- _includes/docs/env/intellij-idea/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/intellij-idea/title.md -->
<!-- 2. include docs/env/intellij-idea/title.md useMDHead="###" -->

{% assign stm = "IntelliJ IDEA Community Edition" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
