<!-- _includes/docs/env/xcode/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/xcode/title.md -->
<!-- 2. include docs/env/xcode/title.md heading="###" -->

{% assign stm = "Xcode" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
