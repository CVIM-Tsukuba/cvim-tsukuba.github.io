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
          position: 50% -10%
          shape: ellipse
          size: 80% 80%
    content:
      eyebrow: 筑波大学
      title: 画像情報研究室
      text: Computer Vision and Image Media Lab.
      primary_action:
        text: 研究テーマを見る
        url: /projects/
        style: gradient
      secondary_action:
        text: 入室希望の方へ
        url: /join/
        style: ghost

  - block: markdown
    content:
      text: |-
        画像情報や計算メディアを研究の中心に据え、世界最先端の研究に取り組む筑波大学の研究室です。

        コンピュータビジョン、拡張現実、複合現実感技術、自由視点映像、多視点映像、映像認識理解、コンピュータヒューマンインタラクションなどの基礎技術をベースに、研究・教育・社会実装を進めています。
    design:
      spacing:
        padding: ['1.5rem', '0', '2rem', '0']

  - block: collection
    id: research
    content:
      title: 研究テーマ
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
      title: 最新ニュース
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
