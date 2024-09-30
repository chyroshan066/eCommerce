# Ecommerce

Responsive multipage Ecommerce website using HTML, CSS and JavaScript.

## Objectives

* To build amazing professional and responsive website
* To learn the fundamentals of web design
* To learn the concept of flexbox and CSS Grid for layout
* To learn the CSS techniques to create stunning designs and effects
* To use common components and layout patterns
* To learn responsive design using media queries

## Installing / Getting started

A quick introduction of the minimal setup you need to get it running.

## Get an API key

This section explains how to authenticate your app to the <a href = "https://console.cloud.google.com/apis/library/maps-backend.googleapis.com?project=maps-api-437207">Maps Javascript API</a> using our your own API key.
<br>Follow these steps to get an API key:
<br>1. Go to the <a href="https://console.cloud.google.com/">Google Cloud Console</a>.
<br>2. Create or select a project.
<br>3. Click **Continue** to enable the API related services.
<br>4. On the **Credentials** page, get an **API key** (and set the API key restrictions).
<br>5. Once you've got an API key, add it to the following snippet by clicking "YOUR_API_KEY".

```js
<script>
      ((g) => {
        var h,
          a,
          k,
          p = "The Google Maps JavaScript API",
          c = "google",
          l = "importLibrary",
          q = "__ib__",
          m = document,
          b = window;
        b = b[c] || (b[c] = {});
        var d = b.maps || (b.maps = {}),
          r = new Set(),
          e = new URLSearchParams(),
          u = () =>
            h ||
            (h = new Promise(async (f, n) => {
              await (a = m.createElement("script"));
              e.set("libraries", [...r] + "");
              for (k in g)
                e.set(
                  k.replace(/[A-Z]/g, (t) => "_" + t[0].toLowerCase()),
                  g[k]
                );
              e.set("callback", c + ".maps." + q);
              a.src = `https://maps.${c}apis.com/maps/api/js?` + e;
              d[q] = f;
              a.onerror = () => (h = n(Error(p + " could not load.")));
              a.nonce = m.querySelector("script[nonce]")?.nonce || "";
              m.head.append(a);
            }));
        d[l]
          ? console.warn(p + " only loads once. Ignoring:", g)
          : (d[l] = (f, ...n) => r.add(f) && u().then(() => d[l](f, ...n)));
      })({ key: "YOUR_API_KEY", v: "weekly" });
    </script>
```

## Create a div element

For the map to display on a web page, we must reserve a spot for it. Commonly, we do this by creating a named div element.The code below defines an area of the page for your Google map.
``` js
<div id="map"></div>
```
Set the div width and height to greater than 0px for the map to be visible.

## Add a map with a marker

Use the following JavaScript code to add a map with a marker on it.

``` js
// Initialize and add the map
let map;

async function initMap() {
  // The location of Uluru
  const position = { lat: -25.344, lng: 131.031 };
  
  const { Map } = await google.maps.importLibrary("maps");
  const { AdvancedMarkerElement } = await google.maps.importLibrary("marker");

  // The map, centered at Uluru
  map = new Map(document.getElementById("map"), {
    zoom: 4,
    center: position,
    mapId: "DEMO_MAP_ID",
  });

  // The marker, positioned at Uluru
  const marker = new AdvancedMarkerElement({
    map: map,
    position: position,
    title: "Uluru",
  });
}

initMap();
```
If you are using TypeScript, then use the following code.

``` js
// Initialize and add the map
let map;
async function initMap(): Promise<void> {
  // The location of Uluru
  const position = { lat: -25.344, lng: 131.031 };

  const { Map } = await google.maps.importLibrary("maps") as google.maps.MapsLibrary;
  const { AdvancedMarkerElement } = await google.maps.importLibrary("marker") as google.maps.MarkerLibrary;

  // The map, centered at Uluru
  map = new Map(
    document.getElementById('map') as HTMLElement,
    {
      zoom: 4,
      center: position,
      mapId: 'DEMO_MAP_ID',
    }
  );

  // The marker, positioned at Uluru
  const marker = new AdvancedMarkerElement({
    map: map,
    position: position,
    title: 'Uluru'
  });
}

initMap();
```

[comment]: # "## Developing
In order to develop the project, follow these steps"
[comment]: # "### Building
To build the project for deployment, follow these steps"
[comment]: # "### Deploying/Publishing
To deploy the project to a server, follow these steps"
[comment]: # "## Features"
[comment]: # "## Contributing"

## Links

- <a href = "https://github.com/Roshan9807950330/Map-Integration">Project homepage</a>
- Other Projects:
  - <a href = "https://github.com/Roshan9807950330/Text-Utility-App">Text Utility App</a>
  - <a href = "https://github.com/Roshan9807950330/News-App">News App</a>
- <a href = "https://github.com/Roshan9807950330">Profile</a>

[comment]: # "## Licensing"