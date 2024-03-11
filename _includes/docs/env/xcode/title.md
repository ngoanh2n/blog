<!-- _includes/docs/env/xcode/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/xcode/title.md -->
<!-- 2. include docs/env/xcode/title.md isHeading=true -->

{% assign stm = "Xcode" %}
{% assign isHeading = include.isHeading %}

{% if isHeading %}
<{{isHeading}}>{{stm}}</{{isHeading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
