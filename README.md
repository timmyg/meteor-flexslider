meteor-flexslider
=================

Below is an example for Slider w/ thumbnail slider.  See other example at http://flexslider.woothemes.com/

```html
<template name="imagesSlider">
    <div id="slider" class="flexslider">
        <ul class="slides">
        {{#each thisPosting.images}}
            <li>
                <img src="{{url}}"/>
            </li>
        {{/each}}
        </ul>
    </div>
    <div id="carousel" class="flexslider">
        <ul class="slides">
            {{#each thisPosting.images}}
                <li>
                    <img src="{{url}}">
                </li>
            {{/each}}          
        </ul>
    </div>
</template>
```

```coffeescript
Template.imagesSlider.rendered = ->
  $("#carousel").flexslider
    animation: "slide"
    controlNav: false
    animationLoop: false
    slideshow: false
    itemWidth: 210
    itemMargin: 5
    asNavFor: "#slider"

  $("#slider").flexslider
    animation: "slide"
    controlNav: false
    animationLoop: false
    slideshow: false
    sync: "#carousel"
```

Also, I threw the four files in the fonts/ directory into my app's public/fonts directory... probably a better way to do that though.