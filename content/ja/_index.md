---
title: ''
date: 2024-01-01
type: landing

sections:
  - block: markdown
    content:
      title: 画像情報研究室
      subtitle: Computer Vision and Image Media Lab. — 筑波大学
      text: |-
        画像情報や計算メディアを研究の中心に据え、世界最先端の研究に取り組む筑波大学の研究室です。

        コンピュータビジョン、拡張現実、複合現実感技術、自由視点映像、多視点映像、映像認識理解、コンピュータヒューマンインタラクションなどの基礎技術をベースに、研究・教育・社会実装を進めています。
    design:
      background:
        gradient_mesh:
          enable: true
      spacing:
        padding: ['3rem', '0', '3rem', '0']

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
---
