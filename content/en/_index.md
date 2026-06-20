---
title: ''
date: 2024-01-01
type: landing

sections:
  - block: markdown
    content:
      title: Computer Vision and Image Media Lab.
      subtitle: University of Tsukuba
      text: |-
        A laboratory at the University of Tsukuba pursuing world-leading research centered on image information and computational media.

        Building on fundamental technologies such as computer vision, augmented reality, mixed-reality, free-viewpoint and multi-view video, video recognition and understanding, and human-computer interaction, we advance research, education, and real-world deployment.
    design:
      background:
        gradient_mesh:
          enable: true
      spacing:
        padding: ['3rem', '0', '3rem', '0']

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
