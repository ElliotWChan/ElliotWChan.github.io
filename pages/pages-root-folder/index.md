---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
title: "Elliot Chan"
header:
  image_fullwidth: header_unsplash_12.jpg
widget1:
  title: "Blog & Portfolio"
  url: 'http://phlow.github.io/feeling-responsive/blog/'
  image: widget-1-302x182.jpg
  text: 'Every good portfolio website has a blog with fresh news, thoughts and develop&shy;ments of your activities. <em>Feeling Responsive</em> offers you a fully functional blog with an archive page to give readers a quick overview of all your posts.'
widget2:
  title: "Why use this theme?"
  url: 'http://phlow.github.io/feeling-responsive/info/'
  text: '<em>Feeling Responsive</em> is heavily customizable.<br/>1. Language-Support :)<br/>2. Optimized for speed and it&#39;s responsive.<br/>3. Built on <a href="http://foundation.zurb.com/">Foundation Framework</a>.<br/>4. Seven different Headers.<br/>5. Customizable navigation, footer,...'
  video: '<a href="#" data-reveal-id="videoModal"><img src="http://phlow.github.io/feeling-responsive/images/start-video-feeling-responsive-302x182.jpg" width="302" height="182" alt=""/></a>'
widget3:
  title: "Download Theme"
  url: 'https://github.com/Phlow/feeling-responsive'
  image: widget-github-303x182.jpg
  text: '<em>Feeling Responsive</em> is free and licensed under a MIT License. Make it your own and start building. The code is well-documented and explains you how it works.'

permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
---

{::nomarkdown}

  <div class="flex-container">
    <div class="flex-column-left">
        <div class="medium-6 columns">
            {% for post in site.posts limit:1 %}
            <h2><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
                        {% if post.subheadline %}<p class="subheadline">{{ post.subheadline }}</p>{% endif %}
            <p>
                {% if post.meta_description %}{{ post.meta_description | strip_html | escape }}{% else post.teaser %}{{ post.teaser | strip_html | escape }}{% endif %}
                <a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" title="Read {{ post.title | escape_once }}"><strong>{{ site.data.language.read_more }}</strong></a>
            </p>
            {% endfor %}
            <p><strong>{{ site.data.language.more_articles }}</strong></p>
            {% include list-posts entries='300' offset='1' %}
        </div><!-- /.medium-7.columns -->
    </div><!-- /.row -->
    </div>
    <div class="flex-column-right twitter-embed">
      <a class="twitter-timeline" data-width="490" data-tweet-limit="3"
          data-link-color="#30b7f3" data-chrome="noheader nofooter noborders"
          href="https://twitter.com/ElliotWChan?ref_src=twsrc%5Etfw">
        Tweets by ElliotWChan</a>
      <script async src="https://platform.twitter.com/widgets.js">
      </script>
    </div>
  </div>
  {:/}

