{% from "schedule/index.md" import weeks, current_week with context %}
<header class="header-fixed">
{% if current_week == "-1" %}
<div class="w-100 p-1 bg-warning text-center"><md>**This site is not ready yet! The updated version will be available soon.**</md></div >
{% elif current_week == "15" %}
<div class="w-100 p-1 bg-warning text-center"><md>**This site is from a past semester! The current version will be [here](http://www.comp.nus.edu.sg/~{{ module | lower }}) when the new semester starts.**</md></div>
{% endif %}
<navbar placement="top" type="dark">
<a slot="brand" href="{{baseUrl}}/index.html" title="Home" class="navbar-brand"><span class="badge badge-pill badge-{{ module_color }}">{{ module_pair }} <small>{{ period }}</small></span></a>
  <dropdown header="**Schedule**" class="nav-link">
  <li><a href="{{baseUrl}}/schedule/timeline.html" class="dropdown-item"><md>**Full Timeline**</md></a></li>
{% for week in weeks %}
<li><a href="{{ baseUrl }}/schedule/week{{ week.num }}/index.html" class="dropdown-item"> <md>**Week {{ week.num }}** [{{ week.day }}] {% if current_week == week.num %} :fas-arrow-circle-left:{% endif %}</md></a></li>
{% endfor %}
  </dropdown>
  <dropdown header="**Textbook**" class="nav-link">
    <li><a href="{{baseUrl}}/se-book-adapted/index.html" class="dropdown-item">SE Textbook</a></li>
    <li><a href="{{baseUrl}}/programming/index.html" class="dropdown-item">Programming Textbook</a></li>
  </dropdown>
  <li><a href="{{baseUrl}}/admin/te3201-admin.html" class="nav-link"><md>**Admin Info**</md></a></li>
  <dropdown header="**Links**" class="nav-link">
    <li><a href="{{forum_link}}" target="_blank" class="dropdown-item"><md>:fas-comment: Forum</md></a></li>
    <li><a href="{{ baseUrl }}/admin/te3201-admin.html#instructors" class="dropdown-item"><md>:fas-user-tie: Instructors</md></a></li>
    <li><a href="{{announcements_link}}" target="_blank" class="dropdown-item"><md>:glyphicon-bullhorn: Announcements</md></a></li>
    <li><a href="{{repl_link}}" target="_blank" class="dropdown-item"><md>{{ icon_exercise }} `repl.it` link</md></a></li>
    <li><a href="{{files_link}}" target="_blank" class="dropdown-item"><md>:fas-file-upload: Files (slides, handouts etc.)</md></a></li>
    <li><a href="{{baseUrl}}/admin/te3201-admin.html#project" class="dropdown-item"><md>{{ icon_project }} Project Info</md></a></li>
  </dropdown>
  <li slot="right" class="nav-link">
    <form class="navbar-form">
      <searchbar placeholder="Search" algolia menu-align-right ></searchbar>
    </form>
  </li>
</navbar>
</header>
