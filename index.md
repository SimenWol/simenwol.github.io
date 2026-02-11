---
layout: default
---

# 👋 About Me
Hi! I'm Simen Wolters, a game programming student at Breda University of Applied Sciences, specializing as a generalist programmer with experience in gameplay, engine, tools, and graphics development.

I primarily work in C++ and have built both custom engines and Unreal Engine projects in solo and multidisciplinary teams, including leading a team of programmers on a large-scale production project. I enjoy designing scalable systems, solving technical challenges and collaborating closely with designers and artists to create polished gameplay experiences.

Outside of programming, I enjoy playing games, exploring music and films, spending time outdoors, and working on small creative side projects. I'm naturally curious and like learning new skills, both technical and non-technical.

***Currently seeking a game programming internship starting Summer 2026.***

# 🛠️ Skills & Tools
<div class="skills-bar">
  <div class="skill-icon">
    <img src="assets/images/icons/cpp.svg" alt="C++" />
    <div class="tooltip">
      C++<br>
      3+ years of experience in modern C++ (gameplay systems, engine development, rendering, AI, and tooling).
    </div>
  </div>

  <div class="skill-icon">
    <img src="assets/images/icons/vs.png" alt="Visual Studio" />
    <div class="tooltip">
      Visual Studio<br>
      3+ years of experience. Familiar with debugging, profiling, and project configuration tools.
    </div>
  </div>

  <div class="skill-icon">
    <img src="assets/images/icons/vscode.png" alt="Visual Studio Code" />
    <div class="tooltip">
      Visual Studio Code<br>
    </div>
  </div>

  <div class="skill-icon">
    <img src="assets/images/icons/github.svg" alt="Github" />
    <div class="tooltip">
      Github<br> 
      5+ years of experience using source control in personal and team environments. Familiar with GitHub Projects, review process, managing branches, and GitHub Actions for CI/CD.
    </div>
  </div>

  <div class="skill-icon">
    <img src="assets/images/icons/perforce.png" alt="Perforce" />
    <div class="tooltip">
      Perforce<br> 
      2+ years of experience with Perforce and P4V in personal and team environments, including active participation in code reviews through swarm.
    </div>
  </div>

  <div class="skill-icon">
    <img src="assets/images/icons/unreal.svg" alt="Unreal Engine" />
    <div class="tooltip">
      Unreal Engine<br>
      Experience developing gameplay systems in Unreal Engine using C++ and Blueprints in both solo and team environments.
    </div>
  </div>
</div>

# ⭐ Featured Projects

<div class="project-list">
  {% assign sorted_projects = site.projects | sort: "date" | reverse %}
  {% for project in sorted_projects %}
    {% if project.featured == true %}
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

        {% if project.tags %}
          <div class="project-tags">
            {% for tag in project.tags %}
              {% assign tag_up = tag | upcase %}

              <span class="project-tag
                {% if tag_up contains 'ENGINE' %} tag-engine
                {% elsif tag_up contains 'PROJECT' %} tag-project
                {% else %} tag-default
                {% endif %}
              ">
                <strong>{{ tag }}</strong>
              </span>

            {% endfor %}
          </div>
        {% endif %}

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

        {% if project.duration %}
          <p><strong>Duration:</strong> {{ project.duration }}</p>
        {% endif %}

        {% if project.platforms %}
          <div class="project-tags">
          <p><strong>Platforms:</strong></p>
            {% for platform in project.platforms %}
              <span class="project-tag">{{ platform }}</span>
            {% endfor %}
          </div>
        {% endif %}

      </div>
    {% endif %}
  {% endfor %}
</div>

<br>
# 🧩 Other Projects

<div class="project-list">
  {% for project in sorted_projects %}
    {% if project.categories contains "projects" and project.featured != true %}
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

        {% if project.tags %}
          <div class="project-tags">
            {% for tag in project.tags %}
              {% assign tag_up = tag | upcase %}

              <span class="project-tag
                {% if tag_up contains 'ENGINE' %} tag-engine
                {% elsif tag_up contains 'PROJECT' %} tag-project
                {% else %} tag-default
                {% endif %}
              ">
                <strong>{{ tag }}</strong>
              </span>

            {% endfor %}
          </div>
        {% endif %}

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

        {% if project.duration %}
          <p><strong>Duration:</strong> {{ project.duration }}</p>
        {% endif %}

        {% if project.platforms %}
          <div class="project-tags">
          <p><strong>Platforms:</strong></p>
            {% for platform in project.platforms %}
              <span class="project-tag">{{ platform }}</span>
            {% endfor %}
          </div>
        {% endif %}

      </div>
    {% endif %}
  {% endfor %}
</div>