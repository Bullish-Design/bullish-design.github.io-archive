+++
title = "Siteman"
description = "A file-first site manager for Hugo and GitHub Pages."
image = "images/work-siteman.svg"
image_alt = "A file, a Hugo build step, and a finished web page connected in one line."
preview = true
weight = 2
+++

Siteman is a static site manager for Hugo. It is delivered as a devenv module and provides commands to initialize, preview, build, and check a site.

## The system

Siteman keeps authored content at the repository root. It keeps Hugo configuration, layouts, and archetypes under `.siteman/`. The file structure stays visible to site authors while the build tools remain contained.

The module supplies Hugo Extended and the `siteman-*` commands. A site can pin its theme as a Hugo module, build into `public/`, and validate local links before deployment.

The command set covers setup, authoring, preview, build, theme sync, cleanup, and checks. The checker builds the site, lints Markdown and prose, tests local links, and validates the Pages workflow when one exists. The deploy workflow reads GitHub Pages' base URL and sends the configured publish directory to the Pages action.

## Bullish Design's role

Bullish Design develops and maintains siteman. This site uses `siteman-build` to create its published files and `siteman-check` to review its content, internal links, and deployment workflow.
