# vreticle
A gaze directed interface for THREE.js with an event handling system, forked from [neuman/vreticle](https://github.com/neuman/vreticle).

> This package is intended for use in webvr powered games and applications. Webvr is an upcoming standard for the delivery of virtual reality experiences through the web. However, while the standard develops there are many competing systems that must be supported to reach a wide audience, so vreticle is designed to work seamlessly with the [webvr-boilerplate](https://github.com/borismus/webvr-boilerplate) which supports desktop browsers, google cardboard, pure mobile accelerometers, and oculus rift (via firefox and chromium experimental builds).

## How To

Include vreticle

```html
<script src="vreticle.js"></script>
```
Initialize the reticle by handing it the camera you want it attached to.

```javascript
//create gaze interaction manager
var reticle = vreticle.Reticle(camera, 1.5);
scene.add(camera);
```
Define event handler functions for your THREE.js object.

```javascript
var cube = new THREE.Mesh(geometry, material);

cube.ongazelong = function(){
  // this.material = reticle.get_random_hex_material();
  // Do something
}

cube.ongazeover = function(){
  // this.material = reticle.get_random_hex_material();
  // Do something
}

cube.ongazeout = function(){
  // this.material = reticle.default_material();
  // Do something
}
```

Add your THREE.js object to the reticle's collider list!

```javascript
reticle.add_collider(cube);
```

And make sure to tick the reticle during your animation loop.

```javascript
  reticle.reticle_loop();
```
