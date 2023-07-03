---
# Leave the homepage title empty to use the site title
title:
date: 2023-07-03
type: landing

sections:
  - block: hero
    content:
      title: |
        仰 望 星 空
      image:
        filename: starsky.jpg
      text: |
        <br>
        
        欢迎来到我的个人博客！在这里，我与您分享我的心灵世界和思考。通过文字和图像，我与您分享我对星空的热爱和探索，以及人生的思考和体验。无论您是天文爱好者、哲学追寻者还是寻找灵感的人，我希望我的博客能为您带来一份启发和共鸣。
  
  - block: collection
    content:
      title: 近期文章
      subtitle:
      text:
      count: 5
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: post
    design:
      view: card
      columns: '1'
    
  - block: markdown
    content:
      title:
      subtitle: ''
      text:
    design:
      columns: '1'
      background:
        image: 
          filename: 1.jpg
          filters:
            brightness: 1
          parallax: false
          position: center
          size: cover
          text_color_light: true
      spacing:
        padding: ['20px', '0', '20px', '0']
      css_class: fullscreen
      
  - block: markdown
    content:
      title:
      subtitle:
          text: |
    从来没有留心过，所以现在写不出！
    design:
      columns: '1'
---
