### Shaders

> In order to significantly change how the water looks, you would need to edit the water shader  

?> water shader location : AssetRoot/Resources/Shaders/water/waterg.shadergraph

<div class = 'image'>

![creating urp project](addingWater/urpSetup19.png ':class=banner-image  :size=1200' )

</div>

?> Its cleaned up and divided into different subgraphs, so it's fairly easy to change certain elements without understanding the whole shader. 

<div class = 'image'>

![creating urp project](addingWater/urpSetup20.png ':class=banner-image  :size=1200' )

</div>

> shader zoomed out

- There are other shaders you can tune to your liking like : 

?> blur shaders : AssetRoot/Resources/Shaders/blur  

>you can change 2d water blurs

?> droplets shaders : AssetRoot/Resources/Shaders/droplets

>you can change the look of rain post processing shader

?> water simulation compute : AssetRoot/Runtime/SurfaceSimulation/WaterSimulation

>you can change the inner workings of 2d water waves simulation