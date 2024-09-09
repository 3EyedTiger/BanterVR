# Useful Notes

## Components

### Spawn Location

```html
<head>
     ...
     <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
  </head>
<body>
    <a-scene
      sq-disableteleport
      sq-maxoccupancy="number: 64"
      sq-spawnpoint="position: 0 1 0;"
      sq-friendpositionjoinallowed="false"
    >
    ...
</body>
```

### Vidya Player (For Youtube)

Known URLS:

* https://vidya-player.glitch.me/playlist.js
* https://vidya.sdq.st/playlist.js

Example:

```html
  <head>
     ...
     <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
  </head>
  <body>
    ...
    <script
        src="https://vidya-player.glitch.me/playlist.js"
        position="0 0 0"
        rotation="0 0 0"
        scale="1 1 1"
        volume="15"
        instance="unique-space-name"
        one-for-each-instance="true"
        playlist="PLDcXEgXu2q0PSPddoKlUehRpp22PNC_76"
        button-position="-0 0 0"
        button-rotation="0 0 0" 
        button-scale="1 1 1"
        announce="false" 
        spatial="false"
      ></script>
  </body>
```

