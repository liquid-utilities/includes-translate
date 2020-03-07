---
layout: post
title:  "Quick Start"
date:   2020-03-06 11:57:35 -0800
categories: posts
---


This project enables adding Google Translate features to existing Jekyll and/or Shopify built web sites. And by utilizing Git submodules this project may be included within sites hosted by GitHub Pages...


**Installation commands**


```Bash
cd ~/git/hub/__org_name__/__repository__


git checkout gh-pages


mkdir -vp _includes/modules


git submodule add\
 -b master --name "includes-translate"\
 "https://github.com/liquid-utilities/includes-translate.git"\
 "_includes/modules/includes-translate"
```


**Includes example, `_layouts/default.html`**


```HTML
<!--
  Source: https://raw.githubusercontent.com/jekyll/minima/v2.5.0/_layouts/default.html
  License: MIT
  Modified_For: liquid-utilities/includes-translate
-->
<!DOCTYPE html>
<html lang="{{ page.lang | default: site.lang | default: "en" }}">
  {%- include head.html -%}

  <body>
    {%- include header.html -%}

    <main class="page-content" aria-label="Content">
      <div class="wrapper">
        {% include modules/includes-translate/includes-translate.html %}
        {{ content }}
      </div>
    </main>

    {%- include footer.html -%}

  </body>

</html>
```


**Define site defaults, `_config.yaml`**


```YAML
page:
  translate_id: translate_selection
  language: en
  translate_callback: google_translate_callback
  auto_translate: false
```


**Add files to Git staging**


```Bash
git add README.md
git add .gitmodules
git add _config.yaml
git add _includes/modules/includes-translate
git add _layouts/default.html
```


**Commit changes**


```Bash
git commit -F- <<'EOF'
:heavy_plus_sign: Adds `liquid-utilities/includes-translate#1` submodule
EOF
```


**Push to GitHub**


```Bash
git push origin gh-pages
```


**&#x1F389; Excellent &#x1F389;** your site is now ready to begin unitizing code from this project!
