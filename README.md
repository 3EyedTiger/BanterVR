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

Allows for open communal control of one synchronised youtube player.

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

### Individual Vidya Player (For Youtube)

Allows for individualised control of one youtube player, great for unattended use.

Known URLS:

* https://vidya-player.glitch.me/playlist.js
* https://vidya.sdq.st/playlist.js

Example:

```html
<script
      src="https://vidya.sdq.st/playlist.js"
      position="-9.6 -6 25.7"
      rotation="-90 180 0"
      scale="13 17 1"
      volume="15"
      instance="unique-space-name-"
      one-for-each-instance="true"
      playlist="PLDcXEgXu2q0OnSRC0_cT1Pm8twHM9dygx"
      button-position="-10 0.7 1.8"
      button-rotation="0 180 0" 
      button-scale="0.5 0.5 0.5"
      announce="false" 
      spatial="false"
  ></script>
  

    <!-- Individual Player -->
  <script>
      function generateRandomString(length) {
          const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
          let result = '';
          for (let i = 0; i < length; i++) {
              result += characters.charAt(Math.floor(Math.random() * characters.length));
          }
          return result;
      }      

      const scriptTag = document.querySelector('script[src*="https://vidya.sdq.st/playlist.js"]');

      if (scriptTag) {
        // Generate a random 10-character string
        const randomString = generateRandomString(10);

        // Set the `inst` attribute with the random string
        scriptTag.setAttribute('instance', `unique-space-name-${randomString}`);
      }
  </script>
```


### Screencast Player (For Browser Tab / Desktop Sharing)

Put the below snippet in your bullshcript.js

Then use https://sidequestvr.github.io/SideQuest.Banter.Spaces/screen-cast/ to cast a browser tab - swap the "874378434" in the method call with the uniquely assigned value for that session.

```
    async function showScreenCast(id){
        // screencast:
        const url = `https://sidequestvr.github.io/SideQuest.Banter.Spaces/screen-cast/?sid=${id}`;
        const mipMaps = 4;
        const pixelsPerUnit = 1200;
        //const actions = "click2d,0.5,0.5";
        const gameObject = new BS.GameObject("ScreenCastBrowser"); 
        const pageWidth = 1280;
        const pageHeight = 720;
        const browser = await gameObject.AddComponent(new BS.BanterBrowser(url, mipMaps, pixelsPerUnit, pageWidth, pageHeight));
        const transform = await gameObject.AddComponent(new BS.Transform());

        transform.position = new BS.Vector3(-9.6, -6, -25.6);
        transform.localRotation = new BS.Vector3(1 ,-45 ,45);
        transform.localScale = new BS.Vector3(10.2, 11.2, 1);
        // ...
        browser.ToggleInteraction(false);
        // ...
        //browser.RunActions("click2d,0.5,0.5");
    }



    // initialize : USE WITH https://sidequestvr.github.io/SideQuest.Banter.Spaces/screen-cast/
    showScreenCast("874378434");
```'
