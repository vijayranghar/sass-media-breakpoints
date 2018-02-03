## SASS Media breakpoints
A lightweight set of sass mixins for media queries written to make you more productive and make your media queries more readable.

## Installation
- Install sass-media-breakpoints using npm

  `npm install sass-media-breakpoints` 
  
## Advantage
- Easy to use and makes you more productive by not writing lesser code 
- Since sass is compiled, only mixins that you use will be converted to the final css

## Dev
If you want to contribute and add more commonly used mixing, do the following 
 - clone the repo 
 	`git clone https://github.com/vijayranghar/sass-media-breakpoints.git`
 - make changes to the scss files inside `assets` or `index.scss`
 - run `npm run compile`

## Use

- Import sass-media-breakpoints at the beginning of your stylesheet

  `@import "sass-media-breakpoints/assets/index";`

- The module contains a list of easy to use mixins that can be used by incluing them using the `@include` command.

	example 
    ```
    @include desptop {
      .foo {
        font-size: 20px;
      }
    }
    ```
     will generate 
     ```
     @media (min-width: 992px)  {
       .foo {
         font-size: 20px;
       }
     }
     ```
 
 #### Following is the list of available mixins 
 - #### desktop

   ```
   @include desptop {}
   ```
   ```
   @media (min-width: 992px) {}
   ```
 
 - #### tablet
   ```
   @include tablet {}
   ```
   ```
   @media (max-width: 991px) {}
   ```

 - #### tablet-only
   ```
   @include tablet {}
   ```
   ```
   @media (min-width: 768px) and (max-width: 991px) {}
   ```
 
 - #### phone
   ```
   @include tablet {}
   ```
   ```
   @media (max-width: 767px) {}
   ```
 - #### mediaquery
   
    | options     | required |
    |-------------|----------|
    | min-width   | yes      |
    | max-width   | yes      |
    | orientation | no       |
    | ratio       | no       |
    
    ##### min and max width
    
    ```
    @include mediaquery (200, 500) {}
    ```
    ```
    @media (min-device-width: 200px) 
      and (max-device-width: 500px) {
      }
    ```
    
    ##### min, max width and orientation
    ```
    @include mediaquery (200, 500, portrait) {}
    ```
    ```
    @media (min-device-width: 200px) 
      and (max-device-width: 500px)
      and (orientation: $orientation) {
      }
    ```
    
    ##### min, max width and ratio
    ```
    @include mediaquery (200, 500, null, 1) {}
    ```
    ```
    @media (min-device-width: 200px) 
      and (max-device-width: 500px)
      and (-webkit-min-device-pixel-ratio: $ratio)
      and (-moz-device-pixel-ratio: $ratio) {
      }
    ```
    
    ##### min, max width, orientation and ratio
    ```
    @include mediaquery (200, 500, portrait, 1) {}
    ```
    ```
    @media (min-device-width: 200px) 
      and (max-device-width: 500px)
      and (-webkit-min-device-pixel-ratio: $ratio)
      and (orientation: $orientation)
      and (-moz-device-pixel-ratio: $ratio) {
      }
    ```
    
 - #### mq-screen
 	This mixin is exactly the same as `mediaquery` but adds `only screen` to all the media queries 
    
    so, for example 
 	```
    @include mq-screen (200, 500) {}
    ```
    ```
    @media only screen
      and (min-device-width: 200px) 
      and (max-device-width: 500px) {
    }
    ```
    and so on
    
    ##### NOTE
    ###### Although we do not recommend using devide specific media queries, but there are situations when you need to use them.
    
    Following are a list of all device specific media queries
     
 - #### google-pixel
 - #### google-pixel-portrait
 - #### google-pixel-landscape
 - #### google-pixel-xl
 - #### google-pixel-xl-portrait
 - #### google-pixel-xl-landscape
 - #### htc-one
 - #### htc-one-portrait
 - #### htc-one-landscape
 - #### iphone-4
 - #### iphone-4-portrait
 - #### iphone-4-landscape
 - #### iphone-4s
 - #### iphone-4s-portrait
 - #### iphone-4s-landscape
 - #### iphone-5
 - #### iphone-5-portrait
 - #### iphone-5-landscape
 - #### iphone-5s
 - #### iphone-5s-portrait
 - #### iphone-5s-landscape
 - #### iphone-5c
 - #### iphone-5c-portrait
 - #### iphone-5c-landscape
 - #### iphone-5se
 - #### iphone-5se-portrait
 - #### iphone-5se-landscape
 - #### iphone-6
 - #### iphone-6-portrait
 - #### iphone-6-landscape
 - #### iphone-6s
 - #### iphone-6s-portrait
 - #### iphone-6s-landscape
 - #### iphone-6-plus
 - #### iphone-6-plus-portrait
 - #### iphone-6-plus-landscape
 - #### iphone-7
 - #### iphone-7-portrait
 - #### iphone-7-landscape
 - #### iphone-7-plus
 - #### iphone-7-plus-portrait
 - #### iphone-7-plus-landscape
 - #### iphone-8
 - #### iphone-8-portrait
 - #### iphone-8-landscape
 - #### iphone-8-plus
 - #### iphone-8-plus-portrait
 - #### iphone-8-plus-landscape
 - #### iphone-x
 - #### iphone-x-portrait
 - #### iphone-x-landscape
 - #### galaxy-s3
 - #### galaxy-s3-portrait
 - #### galaxy-s3-landscape
 - #### galaxy-s4
 - #### galaxy-s4-portrait
 - #### galaxy-s4-landscape
 - #### galaxy-s5
 - #### galaxy-s5-portrait
 - #### galaxy-s5-landscape
 - #### galaxy-note3
 - #### galaxy-note3-portrait
 - #### galaxy-note3-landscape
 - #### galaxy-s6
 - #### galaxy-s6-portrait
 - #### galaxy-s6-landscape
 - #### windows
 - #### windows-portrait
 - #### windows-landscape
 - #### ipad-1
 - #### ipad-1-portrait
 - #### ipad-2-landscape
 - #### ipad-2
 - #### ipad-2-portrait
 - #### ipad-2-landscape
 - #### ipad-mini
 - #### ipad-mini-portrait
 - #### ipad-mini-landscape
 - #### ipad-air
 - #### ipad-air-portrait
 - #### ipad-air-landscape
 - #### ipad-3
 - #### ipad-3-portrait
 - #### ipad-3-landscape
 - #### ipad-4
 - #### ipad-4-portrait
 - #### ipad-4-landscape
 - #### ipad-pro-97
 - #### ipad-pro-97-portrait
 - #### ipad-pro-97-landscape
 - #### ipad-pro-105
 - #### ipad-pro-105-portrait
 - #### ipad-pro-105-landscape
 - #### ipad-pro-129
 - #### ipad-pro-129-portrait
 - #### ipad-pro-129-landscape
 - #### kindle-fire-hd-7
 - #### kindle-fire-hd-7-portrait
 - #### kindle-fire-hd-7-landscape
 - #### kindle-fire-hd-89
 - #### kindle-fire-hd-89-portrait
 - #### kindle-fire-hd-89-landscape
 - #### nexus-7
 - #### nexus-7-portrait
 - #### nexus-7-landscape
 - #### nexus-9
 - #### nexus-9-portrait
 - #### nexus-9-landscape
 - #### samsung-tab-2
 - #### samsung-tab-2-portrait
 - #### samsung-tab-2-landscape
 - #### samsung-tab-s
 - #### samsung-tab-s-portrait
 - #### samsung-tab-s-landscape
 - #### apple-watch
 - #### moto-360
 - #### laptop-non-retina
 - #### laptop-retina

- [Chris Coyier](https://css-tricks.com/author/chriscoyier/) has documented breakpoints for all these devices really well [here](https://css-tricks.com/snippets/css/media-queries-for-standard-devices/)
