<!-- _includes/docs/env/homebrew/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/homebrew/title.md -->
<!-- 2. include docs/env/homebrew/title.md heading="###" -->

{% assign stm = "Homebrew" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }