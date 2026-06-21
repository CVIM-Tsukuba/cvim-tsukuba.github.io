---
title: ''
date: 2024-01-01
type: landing

sections:
  - block: hero
    id: intro
    design:
      size: compact
      alignment: center
      background:
        gradient:
          type: radial
          start: rgba(124,58,237,0.45)
          end: transparent
          position: "50% -10%"
          shape: ellipse
          size: "80% 80%"
    content:
      eyebrow: University of Tsukuba
      title: Computer Vision and Image Media Lab.
      text: 画像情報研究室
      primary_action:
        text: Research Topics
        url: /en/projects/
        style: gradient
      secondary_action:
        text: Join Us
        url: /en/join/
        style: ghost

  - block: markdown
    content:
      text: |-
        A laboratory at the University of Tsukuba pursuing world-leading research centered on image information and computational media.

        Building on fundamental technologies such as computer vision, augmented reality, mixed-reality, free-viewpoint and multi-view video, video recognition and understanding, and human-computer interaction, we advance research, education, and real-world deployment.
    design:
      spacing:
        padding: ['1.5rem', '0', '2rem', '0']

  - block: collection
    id: research
    content:
      title: Research Topics
      text: ''
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 3
      show_date: false
      show_read_time: false

  - block: collection
    id: news
    content:
      title: Latest News
      text: ''
      count: 6
      filters:
        folders:
          - news
      order: desc
    design:
      view: card
      show_read_time: false
---
