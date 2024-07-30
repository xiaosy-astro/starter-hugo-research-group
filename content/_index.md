---
title: 首页
type: landing

sections:
  - block: slider
    content:
      slides:
        - title: 👋 欢迎来到我的个人博客！
          content: 👋 Welcome to my personal blog!
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: solar-system.png
              filters:
                brightness: 0.7
            position: right
            color: '#666'
        - title: 分享 & 学习 ☕️
          content: '在这里，我与您分享我对星空的热爱与探索，以及人生的思考和体验。'
          align: left
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: nebula-ngc-3132.jpg
              filters:
                brightness: 0.7
            position: center
            color: '#555'
        - title: 探索宇宙奥秘
          content: '希望我的博客能为您带来启发和共鸣。 🌟'
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: universe-spiral.jpg
              filters:
                brightness: 0.5
            position: left
            color: '#333'
          link:
            icon: home
            icon_pack: fas
            text: 开始
            url: ../graduate-student-life/
    design:
      # Slide height is automatic unless you force a specific height (e.g. '400px')
      slide_height: ''
      # Make the slides full screen within the browser window?
      is_fullscreen: true
      # Automatically transition through slides?
      loop: false
      # Duration of transition between slides (in ms)
      interval: 2000
---
<div id="audio-player" style="display: none;">
  {{< audio src="漠河舞厅.mp3" preload="none" controls="true" >}}
</div>
