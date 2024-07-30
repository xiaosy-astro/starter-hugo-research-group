---  
title: 'Home'  
date: 2023-10-24  
type: landing  

sections:  
  - block: hero  
    content:  
      image:  
        filename: solar-system-.jpg  
      cta:  
        label: '**开始**'  
        url: https://wangboting-personal-blog.netlify.app/graduate-student-life/  
      cta_alt:  
        label: 了解更多  
        url: https://wangboting-personal-blog.netlify.app/jiaocheng/  
      text: |-  
        **欢迎来到我的个人博客！在这里，我与您分享我对星空的热爱与探索，以及人生的思考和体验。不论您是天文爱好者、哲学追寻者，还是寻找灵感的人，我希望我的博客能为您带来启发和共鸣。 🌟**  
    design:  
      background:  
        text_color_light: true  
      css_class: fullscreen  
      custom_css: |  
        .hero {  
          position: relative; 
          height: 100vh;  
          overflow: hidden; 
        }  
        .hero img {  
          position: absolute; 
          top: 50%; 
          left: 50%; 
          width: 100%; 
          height: auto;  
          transform: translate(-50%, -50%);   
          z-index: 1; 
        }  
        .hero-text {  
          position: absolute; 
          top: 50%; 
          left: 50%; 
          transform: translate(-50%, -50%); 
          color: white; 
          text-align: center; 
          z-index: 2; 
          padding: 20px; 
          background-color: rgba(0, 0, 0, 0.5);   
        }  
---
