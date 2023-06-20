---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: MGCLsquare.png
widget1:
  title: "Research Highlights"
  url: '/blog/'
  image: 
  text: 'I am primarily interested in how physics-based simulation can be
applied to study biology phenomena. You can find a list of my research interests and publications here.'
widget2:
  title: "Me"
  url: '/CV/'
  image: me.jpg
  text: 'I am a scientist, finishing my PhD in biophysics at the University of
York focused on DNA topology and architectural proteins, now working as a postdoc at the University of Bristol .'
widget3:
  title: "Molecular Simulation"
  url: 'https://en.wikipedia.org/wiki/Molecular_dynamics'
  text: 'Most of the work I do involved computational simulations. Here is a
personal favourite example of the technique, using it to investigate DNA
supercoiling done by <a href="https://agnesnoylab.wordpress.com/">Dr. Agnes Noy.</a>'
  video: '<a href="#" data-reveal-id="videoModal"><img src="images/dancingdna.png" width="300" height="375" alt=""/></a>'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---


<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/fJ4JMXkQzoA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>


