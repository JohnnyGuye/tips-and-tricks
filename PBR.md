# PBR

## About colors

PBR works in linear scale of colors while our monitors have a gamma correction. This means that usually designer works in a gamma modified environment called sRGB. As a result every image supposed to encode real color should be first gamma inverted before being used in PBR. Afterward to keep the smoothness of for our monitors, when all the Physic has been processed, apply gamma correction on it.
This tends to modify the behaviour of distance calculation on light attenuation on which the gamma is also applied. So the usual 1/distance² should be 1/distance since it will be 1/distance² after gamma correction.

## DGF
### The normal distribution D
Tells how distributed the specular light is in respect to the normal of the surface, the bisector of the view vector and the light vector, and the roughness.

Dggx Trowbridge Reitz tends to work better on rough material while Beckmann seems to get some good results on metals. Blinn is old fashion.

### Geometry obstruction G
Tells how shaded by microfacets the surface is. Tends to smoothen the edges of curvy shapes

### Fresnel F
Create the halo when you are the incidence angle is near 0 (all light reflected)

## Lights
Pointlights are the more common lights in real life. And they are easy to render because you just need the angle to the surface you consider and the distance to it to lit up the face. They have an attenuation of the inverse squared distance. (inverse distance with gamma correction)
Spotlights are quite the same but they have a cut off to remove some directions.
A directional light is no more than a pointlight at infinite distance and without attenuation. Well physically it's the case since the sun is our directional light and is emitting from miles and miles away.
