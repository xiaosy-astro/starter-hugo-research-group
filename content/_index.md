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
        
        **相逢即是有缘**
  
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
          filename: coders.jpg
          filters:
            brightness: 1
          parallax: false
          position: center
          size: cover
          text_color_light: true
      spacing:
        padding: ['20px', '0', '20px', '0']
      css_class: fullscreen
  
#  - block: markdown
#    content:
#      title:
#      subtitle:
    #      text: |
     #   {{% cta cta_link="./people/" cta_text="Meet the team →" %}}
#    design:
#      columns: '1'
---
