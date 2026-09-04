---
layout: project
title: "Mantis Engine: Custom OpenXR Game Engine"
date: 2025-04-11
categories: [projects]
featured: true
image: /assets/images/Y2C/main.gif
description: "Mantis Engine is a custom cross-platform C++ engine for Windows and OpenXR-based VR. Development spanned 16 weeks, beginning with an 8-week core engine phase by a team of five programmers, followed by an 8-week production phase with an expanded multidisciplinary team, during which the engine was further extended to support a full game."
contributions: "In-world UI elements (Text, (Animated) Images) | Interactive Buttons (physical & UI-based) | Shooting Mechanics | Core gameplay demo functionality"
tools: "FMOD | Jolt | stb_truetype | EnTT | GLM | ImGui | cereal"
tags:
  - "C++"
  - "CUSTOM ENGINE"
  - "OPENXR"
  - "GROUP PROJECT"
  - "UNIVERSITY"
  - "FEB. - JUN. 2025"
team_size: "Engine Core: 5 Programmers | Production: 8 Programmers, 2 Designers"
platforms:
  - "Windows"
  - "OpenXR"
duration: "Engine Core: 8 weeks (Feb 2025 - Apr 2025) | Production: 8 weeks (May 2025 - June 2025)"
---

# 🦗 Mantis Engine - Custom OpenXR Game Engine

<iframe style="width:100%; max-width:800px; aspect-ratio:16/9;" src="https://www.youtube.com/embed/_X7fqYcqofg?si=FVLMNAiiTyCNxv_H" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br/>
_Mantis Engine_ was a team project focused on building a custom C++ cross-platform game engine for Windows and OpenXR-based VR. The development of the engine spanned over 16 weeks, with an initial 8-week core engine phase by a team of five programmers. This article mainly focuses on this 8 week period.

Additionally, there was an 8-week production phase with an expanded multidisciplinary team, where the aim was to build a game ([Ascension Protocol](https://simenwol.github.io/projects/ascension-protocol/)) with Mantis Engine. During this period the engine was expanded further to support that game's specific needs.

To read more about the production phase, please check out the Ascension Protocol article:<br/>
<a href="https://simenwol.github.io/projects/ascension-protocol/" target="_blank">Click here to read about Ascension Protocol and the production phase of the engine.</a>

---

# My Contributions

- UI System / In-world UI elements
- Interactive Buttons (physical & UI-based)
- Shooting Mechanics
- Core gameplay demo functionality

---

## In-world UI elements / UI System

For our XR engine, we wanted developers to be able to create UI elements directly in the game world. This allowed us to build things such as navigable VR menus, tutortial text, and interactive buttons while keeping the UI compatible with the engine's ECS architecture.

I implement two main UI components:
- **Text Widgets**, including font loading and dynamic text generation using `stb_truetype`.
- **Button Widgets**, designed to support both standard UI interactions and custom in-world interactions.

### Text Widgets

The Text Widget system loads font files into a texture atlas using `stb_truetype`. When a text widget is created, the provided text is used to construct a mesh from the relevant glyphs, with each character represented by its own quad.

Text can also be updated dynamically at runtime. To make the system easier to use, I exposed functionality both directly through the component and through the UI system, allowing developers to update text without needing direct access to the component itself.

I also added helper functionality for creating commonly used text entities, reducing the amount of boilerplate required when creating UI.

<!--```cpp
/// <summary>
/// Function to create a basic textwidget entity.
/// </summary>
/// <param name="entTranslation">Entity's main translation.</param>
/// <param name="entScale">Entity's main scale.</param>
/// <param name="entRot">Entity's main rotation.</param>
/// <param name="fontP">A pointer to the FontData to be used by the textwidget.</param>
/// <param name="text">Text to be displayed. for offset, scale or spacing, call SetText through the system.</param>
/// <param name="textID">The text ID used to identify this textwidget. Defaults to -1</param>
/// <param name="castShadow">Whether or not the textwidget should cast shadows on other objects. Defaults to false</param>
/// <returns>The newly created TextWidget entity.</returns>
static entt::entity CreateTextEntity(glm::vec3 entTranslation,
                                     glm::vec3 entScale,
                                     glm::vec3 entRotation,
                                     std::shared_ptr<FontData> fontP,
                                     std::string text = "",
                                     const int textID = -1,
                                     bool castShadow = false);
```-->

### Button Widgets

Buttons presented a slightly different design challenge. We wanted the engine to support conventional menu buttons, while also allowing developers to create their own interactions. For example, pulling a chain, shooting a target, or pressing a physical button.

To support this, I introduced a `ButtonType` enum that determines how a button is triggered. The initial implementation contained three types:
- `disabled` - the button cannot be triggered.
- `ontouch` - the button is automatically triggered when an entity with a `PressButton` component enters its trigger area.
- `custom` - the button can be triggered externally, allowing developers to implement their own interaction rules.

This approach also leaves the system open to adding new engine-defined button types in the future.

Rather than forcing all button behaviour into the ECS itself, I used a hybrid approach where button activation is handled through events. Develoeprs can bind to the button event and use the provided button ID to determine which button was activated and execute the appropriate gameplay logic.

This made the system relatively simple to integrate while still allowing custom interactions to be built on top of it. For example, the same button system could be used for a conventional VR menu button as well as a button activated by an entirely custom interaction.

---