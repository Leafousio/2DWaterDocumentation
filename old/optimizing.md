### Optimizng Reflections 

> (all) reduce the size of the reflections system render texture (resolution slider in reflections section of water settings), as setting the resolution to 0.5 will reduce the number of pixels needed to render by 4 times, and 0.25 will reduce the number by 16 times

> (topdown) find close sources of water and add the reflector component only when gameobject is close to the water

### Optimizng Obstructions

> reduce the size of the obstructions system render texture (resolution slider in reflections section of water settings), as setting the resolution to 0.5 will reduce the number of pixels needed to render by 4 times, and 0.25 will reduce the number by 16 times

> find close sources of water and add the obstructor component only when gameobject is close to the water

### Optimizng Blur

> (box blur) keep the sampling area under 12

> (gaussian blur) keep the sampling area under 12

> (bokeh blur) keep the quality under 12

> in case of top-down games, don't have more than one water pool with blur active at the same time, and deactivate water pools far away from player 

> note that the quality and sampling area increase the sample rate quadratically (_~n^2 samples_), so quality of 12 means 144 samples for pixel, whitch is reasonable for computers from last 6-8 years,
but impossible for mobile phones. For them you would need to go even lower and can only apply a slight blur.

### Optimizng Simulation

> keep the simulation resolution low, (recommended  2048 , max 4096) for computer games.

> in case of top-down games, don't have more than one water pool with simulation active at the same time, and deactivate water pools far away from player 
