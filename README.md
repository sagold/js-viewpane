# ViewpaneJS

> Feelgood pan and zoomable container


`bower install viewpane`


## usage


```javascript

    var viewpane = new Viewpane($camera, $viewpane, options);

```


### options

```javascript
    {
        // friction used on animation to stop user input
        friction: 0.91,             
        // type of valid positions. May also be "fitBothDimensions"
        typeOfFocus: "fitLargestDimension",     
        // The area to focus camera (bound, rubberband). Default: viewpane-element dimensions
        focus: {x: 2048, y: 1024},
        // perspective of camera. Values 0+. Default 1000  
        perspective: 1000,      
        // perspective origin. Values [0, 1]. Default (0.5, 0.5)    
        origin: {x: 0.5, y: 0.5}
    }
```


## performance

- ensure images are a multiple of 2 (i.e. use 2048x1024, but NOT 20148x1025). Especially on iOS


## known bugs

- sometimes zoomIn does not trigger rubberband animation

- Browserbugs
    - iOS 9.0.x, `transform-style: preserve-3d` flickering 3d layers
        - overflow hidden destroys preserve3d
            http://stackoverflow.com/questions/32639639/ios-9-mobile-safari-has-a-blinking-bug-with-transform-scale3d-and-translate3d)
        -workaround: use js entities instead of css only setup
