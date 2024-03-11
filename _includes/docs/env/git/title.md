<!-- _includes/docs/env/git/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/git/title.md -->
<!-- 2. include docs/env/git/title.md isHeading=true -->

{% assign stm = "Git" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
