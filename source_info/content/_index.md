---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2022-10-24
type: landing
design:
  # Default section spacing
  spacing: '6rem'
sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: me
      text: ''
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/2026_CV_PatricioPerezHenriquez-updated.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      # Use the new Gradient Mesh which automatically adapts to the selected theme colors
      background:
        gradient_mesh:
          enable: true
      # Name heading sizing to accommodate long or short names
      name:
        size: md # Options: xs, sm, md, lg (default), xl
      # Avatar customization
      avatar:
        size: medium # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: circle # Options: circle (default), square, rounded
  
  - block: markdown
    content:
      title: 'Research'
      subtitle: ''
      text: |-
        Specifically, I utilize genetics, advanced microscopy, and quantitative image analysis to decipher how cells communicate and organize, with findings published in Nature Communications, Cell, and other top journals. Deeply committed to evidence-based education, I hold a CIRTL Associate Teaching Certificate and actively mentor undergraduate and graduate students.
        My research focuses on understanding the molecular mechanisms that control plant development, particularly lateral root formation and auxin signaling pathways. Using Arabidopsis as a model system, I investigate how polarized protein localization and hormone gradients coordinate cellular pattern formation in roots and leaves. My work combines molecular genetics, live-cell imaging, and transcriptomics to uncover the hierarchical signals that guide plant morphogenesis.
        
        Current projects include studying receptor-like kinases in root epidermis and deciphering the self-organizing auxin transport systems that pattern developing tissues.
    design:
      columns: '1'
  
  # - block: collection
  #   id: papers
  #   content:
  #     title: Featured Publications
  #     filters:
  #       folders:
  #         - publication
  #       featured_only: true
  #   design:
  #     view: article-grid
  #     columns: 2
  
  # - block: collection
  #   content:
  #     title: Publications
  #     text: 'recent things! '
  #     filters:
  #       folders:
  #         - publication
  #       exclude_featured: false
  #   design:
  #     view: citation
  
  # - block: collection
  #   id: talks
  #   content:
  #     title: Recent & Upcoming Talks
  #     filters:
  #       folders:
  #         - event
  #   design:
  #     view: card
  
  # Commented out - News section (uncomment if you want to add blog posts)
  # - block: collection
  #   id: news
  #   content:
  #     title: Recent News
  #     subtitle: ''
  #     text: ''
  #     page_type: post
  #     count: 5
  #     filters:
  #       author: ''
  #       category: ''
  #       tag: ''
  #       exclude_featured: false
  #       exclude_future: false
  #       exclude_past: false
  #       publication_type: ''
  #     offset: 0
  #     order: desc
  #   design:
  #     view: card
  #     spacing:
  #       padding: [0, 0, 0, 0]
  
  # Removed - Demo promotional block
---