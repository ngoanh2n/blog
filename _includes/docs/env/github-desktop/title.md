<!-- _includes/docs/env/github-desktop/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/github-desktop/title.md -->
<!-- 2. include docs/env/github-desktop/title.md isHeading=true -->

{% assign stm = "GitHub Desktop" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
