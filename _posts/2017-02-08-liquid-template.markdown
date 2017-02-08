---
layout: post
title:  "Langage de template Liquid"
date:   2017-02-08 11:56:22 +0100
categories: notes 
---

Description complète du langage de template Liquid: http://shopify.github.io/liquid/

Pour afficher un bloc brut utiliser les marques "raw":

    {% raw %}
    
        ...here goes raw content... 
     
    {% endraw %}

Les variables définies dans config.yml sont disponibles dans les templates:

    {% raw %} {{ site.title }} {% endraw %} {{ site.title }}
    

Variables disponibles: https://jekyllrb.com/docs/variables/

    site            Sitewide information + configuration settings from _config.yml. See below for details.
    page            Page specific information + the YAML front matter. Custom variables set via the YAML Front Matter will be available here. See below for details.
    layout          Layout specific information + the YAML front matter. Custom variables set via the YAML Front Matter in layouts will be available here.
    content         In layout files, the rendered content of the Post or Page being wrapped. Not defined in Post or Page files.
    paginator       When the paginate configuration option is set, this variable becomes available for use. See Pagination for details. 
    
    
L'en tête "front matter" au début des posts permet de fixer des variables:

    ---
    layout: page
    title: About
    permalink: /about/
    ---
    
    ... 
    
    # {% raw %} {{ page.title }} {% endraw %}
    
Inclure un fichier html:

    {% raw %} {% include my-include.html %} {% endraw %}
    
Commentaires:
    
    {% raw %} 
    {% 
        
        Some stuff ...
        
    %} 
    {% endraw %}

Filtres:

    {% raw %} {{ 'i am now uppercase'|upcase }} {% endraw %} 
    {{ 'i am now uppercase'|upcase }}
    
    
Blocs:

    {% raw %}
    
    {% for post in posts %}
        My title is {{ post.title }}
    {% endfor %}
    
        
    {% if variable_name %}
        variable_name exists
    {% else %}
        variable_name doesn't exist
    {% endif %}
    
    {% endraw %}
        
Lister les pages disponibles:
    
    {% raw %}
    {% for page in site.pages %}
        {{ page.title }}
    {% endfor %}    
    {% endraw %}
    
    {% for page in site.pages %}
        {{ page.title }}
    {% endfor %}