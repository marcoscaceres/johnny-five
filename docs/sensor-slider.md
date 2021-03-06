# Sensor Slider

Run with:
```bash
node eg/sensor-slider.js
```


```javascript
var five = require("johnny-five"),
    board, slider;

board = new five.Board();

board.on("ready", function() {

  // Create a new `slider` hardware instance.
  slider = new five.Sensor({
    pin: "A0",
    freq: 250
  });

  // Inject the `slider` hardware into
  // the Repl instance's context;
  // allows direct command line access
  board.repl.inject({
    slider: slider
  });

  //
  // "change", "slide", "touch", "bend"
  //
  // Fires when value of sensor changes
  //
  slider.scale([ 0, 100 ]).on("slide", function( err, value ) {

    console.log( "slide", value, this.value, this.scaled );

  });
});

// Tutorials
//
// http://www.dfrobot.com/wiki/index.php?title=Analog_Slide_Position_Sensor_(SKU:_DFR0053)

```

## Breadboard

<img src="https://raw.github.com/rwldrn/johnny-five/master/docs/breadboard/sensor-slider.png">

[docs/breadboard/sensor-slider.fzz](https://github.com/rwldrn/johnny-five/blob/master/docs/breadboard/sensor-slider.fzz)



## Devices




## Documentation

_(Nothing yet)_









## Contributing
All contributions must adhere to the [Idiomatic.js Style Guide](https://github.com/rwldrn/idiomatic.js),
by maintaining the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [grunt](https://github.com/cowboy/grunt).

## Release History
_(Nothing yet)_

## License
Copyright (c) 2012 Rick Waldron <waldron.rick@gmail.com>
Licensed under the MIT license.
