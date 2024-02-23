<!-- _includes/docs/env/xcode/ -->

{% assign stm = "Xcode" %}
{% assign heading = include.heading %}

{% if heading %}
<{{heading}}>{{stm}}</{{heading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
