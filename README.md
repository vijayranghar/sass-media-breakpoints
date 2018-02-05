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

  `@import "./node_modules/sass-media-breakpoints/assets/index";`

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
 
 **Following is the list of available mixins**
- **desktop**

 ```
 @include desptop {}
 ```
 ```
 @media (min-width: 992px) {}
 ```

- **tablet**
 ```
 @include tablet {}
 ```
 ```
 @media (max-width: 991px) {}
 ```

- **tablet-only**
 ```
 @include tablet {}
 ```
 ```
 @media (min-width: 768px) and (max-width: 991px) {}
 ```

- **phone**
 ```
 @include tablet {}
 ```
 ```
 @media (max-width: 767px) {}
 ```
- **mediaquery**
 
| options     | required |
|-------------|----------|
| min-width   | yes      |
| max-width   | yes      |
| orientation | no       |
| ratio       | no       |
  
  *min and max width*
  
  ```
  @include mediaquery (200, 500) {}
  ```
  ```
  @media (min-device-width: 200px) 
    and (max-device-width: 500px) {
    }
  ```
  
  *min, max width and orientation*
  ```
  @include mediaquery (200, 500, portrait) {}
  ```
  ```
  @media (min-device-width: 200px) 
    and (max-device-width: 500px)
    and (orientation: $orientation) {
    }
  ```
  
  *min, max width and ratio*
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
  
  *min, max width, orientation and ratio*
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
  
- **mq-screen**
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
  
  *NOTE*
  Although we do not recommend using devide specific media queries, but there are situations when you need to use them.
  
  Following are a list of all device specific media queries
  
  Each mixin can be either used without any param or with a single param to set the orientation which can be either landscape or portrait
  
  example Use 
  
  ```@inclue iphone-5 {}```
  
  ```@inclue iphone-5(landscape) {}```
  
  ```@inclue iphone-5(portrait) {}```
    
- **google-pixel**
- **google-pixel(landscape | portrait)**
- **google-pixel-xl**
- **google-pixel-xl-(landscape | portrait)**
- **htc-one**
- **htc-one(landscape | portrait)**
- **iphone-4**
- **iphone-4(landscape | portrait)**
- **iphone-4s**
- **iphone-4s(landscape | portrait)**
- **iphone-5**
- **iphone-5(landscape | portrait)**
- **iphone-5s**
- **iphone-5s(landscape | portrait)**
- **iphone-5c**
- **iphone-5c(landscape | portrait)**
- **iphone-5se**
- **iphone-5se(landscape | portrait)**
- **iphone-6**
- **iphone-6(landscape | portrait)**
- **iphone-6s**
- **iphone-6s(landscape | portrait)**
- **iphone-6-plus**
- **iphone-6-plus(landscape | portrait)**
- **iphone-7**
- **iphone-7(landscape | portrait)**
- **iphone-7-plus**
- **iphone-7-plus(landscape | portrait)**
- **iphone-8**
- **iphone-8(landscape | portrait)**
- **iphone-8-plus**
- **iphone-8-plus(landscape | portrait)**
- **iphone-x**
- **iphone-x(landscape | portrait)**
- **galaxy-s3**
- **galaxy-s3(landscape | portrait)**
- **galaxy-s4**
- **galaxy-s4(landscape | portrait)**
- **galaxy-s5**
- **galaxy-s5(landscape | portrait)**
- **galaxy-note3**
- **galaxy-note3(landscape | portrait)**
- **galaxy-s6**
- **galaxy-s6(landscape | portrait)**
- **windows**
- **windows(landscape | portrait)**
- **ipad-1**
- **ipad-1(landscape | portrait)**
- **ipad-2**
- **ipad-2(landscape | portrait)**
- **ipad-mini**
- **ipad-mini(landscape | portrait)**
- **ipad-air**
- **ipad-air(landscape | portrait)**
- **ipad-3**
- **ipad-3(landscape | portrait)**
- **ipad-4**
- **ipad-4(landscape | portrait)**
- **ipad-pro-97**
- **ipad-pro-97(landscape | portrait)**
- **ipad-pro-105**
- **ipad-pro-105(landscape | portrait)**
- **ipad-pro-129**
- **ipad-pro-129(landscape | portrait)**
- **kindle-fire-hd-7**
- **kindle-fire-hd-7(landscape | portrait)**
- **kindle-fire-hd-89**
- **kindle-fire-hd-89(landscape | portrait)**
- **nexus-7**
- **nexus-7(landscape | portrait)**
- **nexus-9**
- **nexus-9(landscape | portrait)**
- **samsung-tab-2**
- **samsung-tab-2(landscape | portrait)**
- **samsung-tab-s**
- **samsung-tab-s(landscape | portrait)**
- **apple-watch**
- **moto-360**
- **laptop-non-retina**
- **laptop-retina**

- [Chris Coyier](https://css-tricks.com/author/chriscoyier/) has documented breakpoints for all these devices really well [here](https://css-tricks.com/snippets/css/media-queries-for-standard-devices/)
     
