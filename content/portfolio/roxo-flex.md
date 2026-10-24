+++
title = "Roxo Flex"
description = "A configurable Hugo theme for studio, team, and portfolio sites."
image = "images/work-roxo.svg"
image_alt = "Layered page shapes with a plum frame and coral index marks."
preview = true
weight = 1
+++

Roxo Flex is a Hugo theme for studios, teams, and project portfolios. Each site controls its own brand, content, section order, and visual style.

## The design problem

The original theme supplied a useful page structure, but its templates used deprecated Hugo data access. Its counter fields also disagreed with the supplied example data. Roxo Flex keeps the portfolio layout and rebuilds the theme for current Hugo.

## The system

Site owners set colors, type, spacing, icons, and image treatment in their Hugo configuration. The homepage reads its sections and order from a content file. The theme supplies layouts and reusable content patterns; each site supplies its own images and words.

The theme keeps its structure flexible without moving site content into the theme. It supports ordered homepage sections, project pages, local font files, and icons. A site can add a link preview for one of its own pages. The preview reads that page's title, description, and image instead of fetching outside content.

## Bullish Design's role

Bullish Design maintains this fork of [sitepins/roxo-hugo](https://github.com/sitepins/roxo-hugo). The current theme adds site-owned style settings, local font support, mobile navigation, and link previews. Its examples exercise both neutral and muted palettes at desktop and mobile widths. The fork keeps the upstream Git history and MIT license.

Read the [Roxo Flex source repository](https://github.com/Bullish-Design/roxo-flex).
