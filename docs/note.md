# Markdown
- Emoji Cheat Sheet: https://github.com/ikatyang/emoji-cheat-sheet

# Platform Statement: IF
<!-- macOS -->
{% if platform == "macos" %}

{% endif %}

<!-- Windows -->
{% if platform == "windows" %}

{% endif %}

<!-- All -->
{% if platform == nil %}

{% endif %}

# Platform Statement: IFELSE
<!-- MACOS & WINDOWS -->
{% if platform %}
<!-- macOS -->
{% if platform == "macos" %}

<!-- Windows -->
{% else %}

{% endif %}

<!-- All -->
{% else %}

{% endif %}
