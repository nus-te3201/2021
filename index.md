{% from "schedule/index.md" import weeks, current_week with context %}
{% if current_week in ["-1", "0", "14", "15"] %}
<div id="website-content">

<include src="admin/{{ module | lower }}-admin.md" />
</div>
{% else %}
<include src="schedule/index.md" />
{% endif %}
