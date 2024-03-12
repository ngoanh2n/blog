<!-- _includes/docs/env/xcode/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/xcode/title.md -->
<!-- 2. include docs/env/xcode/title.md useMDHead="###" -->

{% assign stm = "Xcode" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
