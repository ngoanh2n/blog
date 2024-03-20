# Markdown
- Emoji Cheat Sheet: https://github.com/ikatyang/emoji-cheat-sheet

# Platform Statement: IF
<!-- MACOS -->
{% if platform == "macos" %}

{% endif %}

<!-- WINDOWS -->
{% if platform == "windows" %}

{% endif %}

<!-- PLATFORMS -->
{% if platform == nil %}

{% endif %}

# Platform Statement: IFELSE
<!-- MACOS & WINDOWS -->
{% if platform %}

<!-- MACOS -->
{% if platform == "macos" %}

<!-- WINDOWS -->
{% else %}

{% endif %}

<!-- PLATFORMS -->
{% else %}

{% endif %}
