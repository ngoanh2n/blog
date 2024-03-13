<!-- _includes/docs/env/homebrew/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/homebrew/title.md -->
<!-- 2. include docs/env/homebrew/title.md useMDHead="###" -->

{% assign stm = "Homebrew" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }