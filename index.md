---
layout: default
---

# About self
This portfolio is a WIP, please come back later!

# Skills
- TBA

# Projects

<div class="project-list">
  {% assign sorted_projects = site.projects | sort: "date" | reverse %}
  {% for project in sorted_projects %}
    {% if project.categories contains "projects" %}
      <div class="project-card">
        {% if project.image %}
          <a href="{{ project.url }}" class="project-image-link">
            <img src="{{ project.image }}" alt="Preview of {{ project.title }}">
          </a>
        {% endif %}

        <h2>
          <a href="{{ project.url }}" class="project-title-link">{{ project.title }}</a>
        </h2>

        <p><strong>Date:</strong> {{ project.date | date: "%B %-d, %Y" }}</p>

        {% if project.description %}
          <p>{{ project.description }}</p>
        {% endif %}
        
        <p><a href="{{ project.url }}" class="read-more-link">Read more →</a></p>

        {% if project.contributions %}
          <p><strong>My Contributions:</strong> {{ project.contributions }}</p>
        {% endif %}

        {% if project.tools %}
          <p><strong>Engine/Tools:</strong> {{ project.tools }}</p>
        {% endif %}

        {% if project.team_size %}
          <p><strong>Team Size:</strong> {{ project.team_size }}</p>
        {% endif %}

        {% if project.platforms %}
          <p><strong>Platforms:</strong> {{ project.platforms }}</p>
        {% endif %}

        {% if project.duration %}
          <p><strong>Duration:</strong> {{ project.duration }}</p>
        {% endif %}

      </div>
    {% endif %}
  {% endfor %}
</div>