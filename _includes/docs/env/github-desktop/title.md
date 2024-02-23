<!-- _includes/docs/env/github-desktop/ -->

{% assign stm = "GitHub Desktop" %}
{% assign heading = include.heading %}

{% if heading %}
<{{heading}}>{{stm}}</{{heading}}>
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
