# Find errors on this file with http://www.yamllint.com/

# Chulapa docs: https://dieghernan.github.io/chulapa/docs/02-config

# XX. Installing Chulapa

# With remote theme
remote_theme: dieghernan/chulapa

# With gem based method do this instead
# theme: chulapa-jekyll
# And at this to your Gemfile
# gem install 'chulapa-jekyll'


# A. Site Settings /SEO options
# Overall options for your site, would affect your site SEO
# Default values are explained
locale                  :     #default["en-US"] format language-TERRITORY , e.g fr, en-GB, es-MX, pt-BR
title                   :     #default["repository_name"]
title_separator         :     #default [" | "]
subtitle                :     #default [your-repository-tagline]
description             :     #default [your-repository-tagline]
url                     :     #See baseurl - On Github Pages you may leave it blank - If you use CNAME use your domain
baseurl                 :     #On Github Pages you may leave it blank. Have a look to: https://byparker.com/blog/2014/clearing-up-confusion-around-baseurl/
words_per_minute        :     #default[200]
timezone                :     #"Europe/Madrid ,see https://jekyllrb.com/docs/configuration/options/ and https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

# SEO
og_image                :     #default[author.avatar (see below)] or [github-avatar]
twitter_site            :     #Avoid @
author:
  name                  :     # Name Surname Company
  avatar                :     # Try a square file. Info: Your github avatar on https://github.com/[USERNAME].png
  location              :     # New York, USA
  links:
    - url:  #A link or email: https://twitter.com/jack, mail@example.com
      icon: # A Fontawesome code: fab fa-twitter - see https://fontawesome.com/
      label: # A Label for the icon: Twitter
    - url:  # Another link
      icon: # Another FontAwesome code
      label: # Another label

fa_version: #default ["6"] Use 6 or 5
fa_kit_code: # Your FontAwesome kit code. If not provided a free hosted version (slower) will be loaded:  https://fontawesome.com/
fa_v4_support: #Bool Add FontAwesome 4 support
# Web tracking - Google services https://analytics.google.com/analytics/web/
# gtag_id is the preferred option, see https://developers.google.com/analytics/devguides/collection/gtagjs/migration?hl=en
# analytics provided for backwards compatibility
gtag_id                 :
analytics_id            :

# Search providers
# Available free search engines:
# - lunr https://lunrjs.com/
# - algolia v4 https://www.algolia.com/ - needs further configuration
# - google custom search engine https://cse.google.es/
search:
  provider              : algolia #Select a provider for enable search: lunr, algolia, google
  label                 :  #default ["Search"] Text on navbar when search is enabled
  landing_page          :  #default ["/search"] Link on navbar
  lunr_maxwords         :  #default [30] lunr only - May slow down your site build
  algolia_logo          :  true #Displays algolia logo. Should be set to true if you are on a community plan, otherwise false.

google_cse_id: #Your cse id
# This site uses jekyll-algolia plugin https://community.algolia.com/jekyll-algolia/
# Recommended additional configuration provided, could be modified. Add your own parameters
algolia:
  application_id        : #As per your Algolia account
  index_name            : #As per your Algolia account
  search_only_api_key   : #As per your Algolia account
  files_to_exclude:         #Optional
    - _layouts/*.html
    - _includes/*.html
    - docs/_pages/*
    - docs/blog/*
  extensions_to_index:      #Optional
    - html
    - md
  searchableAttributes:     #Optional
    - title
    - headings
    - unordered(content)
    - unordered(subtitle)
    - unordered(categories)
    - unordered(collection)
    - unordered(tags)
  customRanking:            #Optional
    - desc(include_on_search)
    - desc(title)
    - desc(content)
    - desc(subtitle)

comments:
  provider:         #Enable comments via Disqus, giscus, Cactus.chat, cusdis
  disqus_shortname: #Your site id : check your address https://{{ disqus.shortname }}.disqus.com/admin/
  cactus_shortname: #Your site id as registered with Cactus.chat
  cusdis_app_id:    # Your cusdis app id
  cusdis_host:      # Optionally you can use your own host
  website_id:       # Welcomments id



# B. Navigation
# Configure your navbar and the footer of your site

# Navbar:
#   "brand" options would be set on the left side of your navbar
#   "nav" would be set on the right side. Two-level nav links available
navbar:
  style     :  #default is the classical top navbar, set "fab" for a floating action button navbar or "dual"
  expand    :  # At which device size expand the navbar menu. default[md] https://getbootstrap.com/docs/4.5/layout/overview/
  brand:
    title   :  # Title in navbar
    url     :  # default["url/baseurl"]
    img     :  # An small image, try 30x30px
  nav:
  - title   : # Label
    url     : # url
  - title   : # Label submenu
    child:
     - title: # Child label
       url  : # child url
     - title: # Child label
       url  : # child url

#Social links to be placed on your site footer
footer:
  links:
    - label : #Label
      icon  : # Fontawesome 5 icon
      url   : # A link or email: https://twitter.com/jack, mail@example.com
  copyright: # default is © <year> <name>

# C. Theme Settings
# Google Fonts https://fonts.google.com/, add as many as you need
googlefonts:
 # - url : # 'https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap'

# Theme and colors
chulapa-skin:
  highlight     :  # default["default"]
  skin         :  # Optional predefined skins
  autothemer    :  # Bool: Use autotheming
  vars          :
    primary     :   #default ["#007bff"] - Bootstrap blue

# D. Jekyll Defaults and collections: see https://jekyllrb.com/

# Blog pagination: on this site /blog/index.html. https://jekyllrb.com/docs/pagination/
paginate: 4
paginate_path: "/blog/page:num/"
paginator_maxnum: 3  #default[3] Custom: max of number to be displayed on the paginator


# Collections https://jekyllrb.com/docs/step-by-step/09-collections/
collections:
  demo:
    output: true
    permalink: /demo/:name
  docs:
    output: true
    permalink: /docs/:name
  skins:
    output: true
    permalink: /skins/:name
collections_dir     : docs/collections
permalink           : /:year:month:day_:title/


# Defaults https://jekyllrb.com/docs/configuration/front-matter-defaults/
defaults:
  -
    scope:
      path: ""
    values:
      layout: "default"
      header_type: "base"
      include_on_search   : false
      cloudtag_url        : "/tags"       #This is where the link on tags would redirect
      cloudcategory_url   : "/categories" #This is where the link on categories would redirect
  -
    scope:
      path: ""
      type: "posts"
    values:
      header_type       : "post"
      include_on_search : true
      include_on_feed   : true
      show_date         : true
      show_related      : true
      show_bottomnavs   : true
      show_sociallinks  : true
      show_comments     : true
      show_tags         : true
      show_categories   : true
      show_author       : true
      show_toc          : false
  -
    scope:
      path: ""
      type: "demo"
    values:
      header_type       : "hero"
      show_related      : true
      show_bottomnavs   : true
      show_sociallinks  : true
      include_on_search : true
      include_on_feed   : true




# XX. Other settings - no need to modify
# HTML Compression
# - https://jch.penibelst.de/
compress_html:
  clippings: all
  blanklines: true

plugins:
  - jekyll-github-metadata
  - jekyll-paginate
  - jekyll-include-cache
  - jekyll-sitemap

# Exclude these files from production site
exclude:
  - LICENSE
  - README.md
  - Gemfile
  - vendor
  - /docs # ignore Chulapa /docs
  - /test # ignore Chulapa /test
  - github-metrics.svg

include:
 - _pages

# Conversion
markdown: kramdown
highlighter: rouge
lsi: false
excerpt_separator: "\n\n"
incremental: false

# Markdown Processing
kramdown:
  input: GFM
  hard_wrap: false
  auto_ids: true
  footnote_nr: 1
  footnote_backlink: '&uarr;'
  entity_output: as_char
  toc_levels: 2..6
  smart_quotes: lsquo,rsquo,ldquo,rdquo
  enable_coderay: false

# Sass/SCSS
sass:
  sass_dir: _sass
  style: compressed # https://sass-lang.com/documentation/file.SASS_REFERENCE.html#output_style
