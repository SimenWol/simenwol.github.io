---
layout: project
title: "Suck It Up! - Programming Lead | Steam Release"
date: 2026-06-29
categories: [projects]
featured: true
image: /assets/images/Y3G/main.gif
description: "Programming Lead for a 25+ member university team, an Unreal Engine title released on Steam in June 2026. Responsible for coordinating a team of 7 programmers and guiding the technical side of development."
contributions: "Team Leadership | Gameplay Systems | Code Reviews | Release & Marketing Management"
tools: "C++ & Blueprints with Unreal Engine"
tags:
  - "C++"
  - "UNREAL ENGINE"
  - "GROUP PROJECT"
  - "UNIVERSITY"
  - "NOV. 2025 - JUN. 2026"
team_size: "25+ (7 programmers, 7 designers, 10 artists, 5+ outsourced)"
platforms:
  - "Windows"
duration: "24 weeks (November 2025 - June 2026)"
---

# 🧹 Suck It Up! - A vacuum-powered Action-Adventure

<iframe style="width:100%; max-width:800px; aspect-ratio:16/9;" src="https://www.youtube.com/embed/kXotraWf-Fw?si=n0sB25ahmnxbz4M2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br>
_Suck It Up!_ is an action-adventure where players take the role of an exterminator tasked with clearing Cloud Town of its growing critter infestation. Armed with a vacuum-powered toolkit, players must capture pests and restore order to the city.

<a href="https://store.steampowered.com/app/4515400/Suck_It_Up/" target="_blank">Click here to visit our game page!</a>

---

# My Contributions

- **Programming Lead**: Led and coordinated the programming team while guiding technical decisions.
- **Release & Marketing Management**: Coordinated development milestones and acted as liaison between the team and extenral marketing support.
- **QA, Profiling & Performance Standards**: Established quality standards, performance targets and profiling practices to maintain stable frame rates and game quality.
- **Gameplay Systems**: Implemented gameplay features including the pulley system and gameplay prototypes.

Below I will go over some of these in more detail:

---

## Programming Lead

Halfway through pre-production _(about 8 weeks into the project)_, I took over the role of programming lead. Since then, I've been guiding technical development and team coordination, which includes:

- Led and coordinated a team of 7 programmers, organizing tasks, resolving blockers, and coordinating development across gameplay, systems, and tools to keep the team on schedule for release.
- Defined and maintained coding standards and workflow practices to ensure consistent architecture and maintainable Unreal C++ code across the programming team.
- Maintained alignment between programmers, designers, artists, and production through frequent check-ins and cross-discipline meetings.
- Resolved communication issues within the team through direct conversations and mediation to maintain a productive and positive development environment.
- Managed programming workload and coordinated closely with design and art teams to ensure technical feasibility and smooth feature integration.
- Communicated development progress and technical updates to external stakeholders.
- Conducted code reviews to maintain code quality and provided technical direction on game systems, helping guide technical implementation decisions across the team.

---

## Release & Marketing Management

During the later stages of the project, I assisted with preparing for the game's release and marketing efforts.

Together with other leads and our producer, we established release milestones and defined which features each release would ship with. I then helped ensure that these deadlines were met by coordinating with the programming team and monitoring development progress.

For marketing, our team collaborated with an external marketing student. I acted as the main point of contact between the development team and the marketing collaborator. While they led the creative side of marketing (such as social media posts, marketing materials, and copywriting), I was responsible for coordinating communication, ensuring marketing tasks were properly delegated within the team, and making sure deadlines for marketing assets were met.

---

## QA, Profiling & Performance Standards

During the later stages of the project, I took on responsibility for QA.

This meant I spent a lot of time prioritizing, validating, tracking, and fixing bugs in the project. As well as profiling the game to identify any bottlenecks and areas that could be improved.

Early in the project, I helped establish quality standards, performance targets, and profiling practices to set a quality bar for the game.

---

## Gameplay Systems

While I had less time than usual for programming due to my lead work, I still worked on a few systems throughout the project.

Early on in the project, I created some early gameplay prototypes and some small Unreal Engine C++ components to speed up development/prototyping:

- An early version of the attachable component, where if an object had this component, it would get stuck to the vacuum's nozzle rather than get sucked up completely:

<iframe style="width:100%; max-width:800px; aspect-ratio:16/9;" src="https://www.youtube.com/embed/NJsCBHIqznw?si=NuISC5tqFQHQ1Ak9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br/>
- A few helper C++ components, which sped up prototyping by moving some of the commonly used behaviour to a component that could simply be dragged onto the actor. Below two examples:

The first being a C++ component that made it trivial to make an enemy, or part of it, look towards the player or any other specified actor.

<iframe style="width:100%; max-width:800px; aspect-ratio:16/9;" src="https://www.youtube.com/embed/V11nzVwBb3I?si=pC95oI5UjNHcAvpH" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br/>
The second being a C++ component that made it easy for an actor to move towards the player or another specified actor, using whatever movement system/component the actor already has.

<iframe style="width:100%; max-width:800px; aspect-ratio:16/9;" src="https://www.youtube.com/embed/PeGDKzLQgVk?si=shnWwIGCN_Uz8NzC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br/>

- Later on in the project, I developed a moduoar a pulley system for an earlier traversal-focused section. The system was later discontinued when the game's design shifted toward combat.

The system was made fully in C++, and worked as follows:

- You can place turning points, and a rope will automatically be generated between these points (as well as the endpoints when you add them).
- The endpoints are detached from the system and can be swapped out, making it trivial to add new endpoints as the system was modular. At the time of the system being discontinued, there were currently two variants:
  - `Suckable endpoint` - if you suck this part with your vacuum, it'll attach to the nozzle, and then you can walk back to pull, and certain things happen (based on how the pulley is configured).
  - `Platform endpoint` - The platform can move if the player 'pulls' on the pulley via the suckable point on the other end of the pulley upon which the platform will move towards the next turning point, and can be locked after moving a certain distance.

The first video shows how this system could be configured / placed down by a designer and an early version of how it worked in-game.

<iframe style="width:100%; max-width:800px; aspect-ratio:16/9;" src="https://www.youtube.com/embed/bQ864kYG2NA?si=tCOXVCbmP0wHDve2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br/>
The second video shows what the system looked like at the moment it got discontinued, with the player movement affecting the platform's movement.

<iframe style="width:100%; max-width:800px; aspect-ratio:16/9;" src="https://www.youtube.com/embed/BipKNGSsk78?si=BYNzIHIrZN5IZshd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br/>
