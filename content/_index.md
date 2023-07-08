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
        filename: welcome.jpg
      text: |
        <br>
        
        &emsp;&emsp;欢迎来到我的个人博客！在这里，我与您分享我的心灵世界和思考。通过文字和图像，我与您分享我对星空的热爱和探索，以及人生的思考和体验。无论您是天文爱好者、哲学追寻者还是寻找灵感的人，我希望我的博客能为您带来一份启发和共鸣。
  
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
    
  - block: collection
    content:
      title: 近期文学
      subtitle: 书籍是人类进步的阶梯！
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
      page_type: wenxue
    design:
      view: card
      columns: '1'

  - block: collection
    content:
      title: 近期教程
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
      page_type: jiaocheng
    design:
      view: card
      columns: '1'



---
