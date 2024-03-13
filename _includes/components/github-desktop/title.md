<!-- _includes/docs/env/github-desktop/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/github-desktop/title.md -->
<!-- 2. include docs/env/github-desktop/title.md heading="###" -->

{% assign stm = "GitHub Desktop" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
