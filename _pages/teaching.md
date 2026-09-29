---
layout: default
title: Teaching
permalink: /teaching/
---

<div id="teachingid">

<h1>Teaching</h1>

<p>
Courses taught in nuclear engineering, reactor physics,
and computational reactor analysis.
</p>

<h2>{{ site.current_academic_year }}</h2>

{% for course in site.courses %}
{% if course.current %}

<div class="course-card">

  <h3>
    <a href="{{ course.url | relative_url }}">{{ course.title }}</a>
  </h3>

  <p class="course-meta">
    {% if course.code %}<strong>{{ course.code }}</strong>{% endif %}
    {% if course.credits %} · {{ course.credits }} SKS{% endif %}
    {% if course.level %} · {{ course.level }}{% endif %}
  </p>

  {% if course.description %}
  <p>{{ course.description }}</p>
  {% endif %}

  <p>
    <a href="{{ course.url | relative_url }}">Course page →</a>
  </p>

</div>

{% endif %}
{% endfor %}


<h2>Previous Courses</h2>

{% for course in site.courses %}
{% unless course.current %}

<p>
  <a href="{{ course.url | relative_url }}">
    <strong>{{ course.title }}</strong>
  </a>
  {% if course.code %} — {{ course.code }}{% endif %}
  {% if course.semester %} — {{ course.semester }}{% endif %}
</p>

{% endunless %}
{% endfor %}

</div>