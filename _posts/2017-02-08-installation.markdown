---
layout: post
title:  "Installation et lancement de Jekyll"
date:   2017-02-08 11:56:22 +0100
categories: notes 
---

Installation:

        $ sudo apt-get install ruby ruby-dev
        $ sudo gem install jekyll bundler

Créer un nouveau projet et le servir:

        $ jekyll new new-project
        $ cd new-project
        $ jekyll serve

Servir avec les brouillons:
    
        $ jekyll serve --draft

Aide pour traitement des erreurs:

        $ jekyll build --trace

