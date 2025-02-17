# headless-three
This library aims for headless rendering of three.js scenes based on models by common CAD formats.

Currently supports IFC models.

## Setup
This library uses a custom build of web-ifc-three.  Clone both as sibling directories, then build in turn.

*The relative paths matter and are harcoded*.
```
> git clone https://github.com/bldrs-ai/web-ifc-three   # a custom fork of web-ifc-three
> git clone https://github.com/bldrs-ai/headless-three
> cd web-ifc-three/web-ifc-three
web-ifc-three/web-ifc-three> npm i
web-ifc-three/web-ifc-three> node build.esb.js
Build succeeded.
web-ifc-three/web-ifc-three> cd dist
web-ifc-three/web-ifc-three/dist> npm pack
web-ifc-three/web-ifc-three/dist> ls web-ifc-three-0.0.134.tgz
web-ifc-three-0.0.134.tgz
web-ifc-three/web-ifc-three/dist> cd ../../../headless-three
headless-three> yarn install
```

## Run the tool
```
# Grab the coords from a model on Bldrs, e.g. the default homepage:
#   https://bldrs.ai/share/v/p/index.ifc#c:-150.147,-85.796,167.057,-32.603,17.373,-1.347
#
# Then add them as an arg after the model filename:
headless-three> node src/headless.js index.ifc -150.147,-85.796,167.057,-32.603,17.373,-1.347 && open screenshot.png
```

Example render of index.ifc:
![index.ifc rendered to screenshot.png](https://github.com/bldrs-ai/headless-three/blob/main/screenshot.png)


## Design

![dataflow](https://github.com/bldrs-ai/headless-three/blob/main/flow.png)
