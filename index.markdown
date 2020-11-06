---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
<div class="container">
  <div class="px-3 py-3 pt-md-5 pb-md-4 mx-auto text-center">
    <h1 class="display-4">DLF Forum 2020 Calendar Files</h1>
  </div>


{% for session in site.data.sessions %}
<div class="session">
  <h2>{{ session.Title }}</h2>

  {{ session.start | date: "%A, %B %d at %I:%M%p"}}

  {% assign file_name = session.Title | replace: " ", "_" | replace: "/", "" | append: ".ics" %}

  <div class="cal"><a href="{{ file_name | prepend: "/assets/events/" }}">ical</a></div>
  <div class="link">Aviary Link: <a href="{{ session.Share_Link }}">{{ session.Share_Link }}</a></div>
  <div class="abstract">{{ session.Description | replace: "|", "<br><br>" }}</div>
</div>
{% endfor %}


</div>

{{site.data.sessions}}
