<!-- _includes/docs/env/github-desktop/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/github-desktop/title.md -->
<!-- 2. include docs/env/github-desktop/title.md useMDHead="###" -->

{% assign stm = "GitHub Desktop" %}
{% assign useMDHead = include.useMDHead %}

{% if useMDHead %}
{{useMDHead}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
