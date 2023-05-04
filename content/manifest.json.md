# Web App Manifest

The web application manifest provides information about an application (such as name, author, icon, and description) in a simplified document. Its main purpose is to create progressive web apps (en-US): web applications that can be installed from the main screen of a device without having to do it through an app store (and other advantages such as offline availability and sending push notifications when changes the content of the application.)

## Interest Links

- [Web.dev - How to add a manifest in web application](https://web.dev/add-manifest/?utm_source=devtools)

- [Developer Mozilla - Web app manifests](https://developer.mozilla.org/en-US/docs/Web/Manifest)

- [Progressier App](https://progressier.com/)

- [Maskable App (To create maskable icons)](https://maskable.app/editor)

- [Create a PWA App Manifest Dynamically](https://javascript.plainenglish.io/create-a-pwa-app-manifest-dynamically-3b3d45340b11)

- [Web.dev - Learn PWA](https://web.dev/learn/pwa/)

- [PWA unique id with web app manifest id property (start_url)](https://developer.chrome.com/blog/pwa-manifest-id/?utm_source=devtools)

- [Support of adaptive icons in PWAs with maskable icons (maskable icons)](https://web.dev/maskable-icon/?utm_source=devtools)

- [What does it take for a Progressive Web Application to be good? (PWA Checklist)](https://web.dev/pwa-checklist/)

- [Service Worker Sample: Custom Offline Page Sample](https://googlechrome.github.io/samples/service-worker/custom-offline-page/)

- [Google Lighthouse (Testing PWA)](https://developer.chrome.com/docs/lighthouse/)

- [Using Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)

- [ServiceWorker - Mozilla Dev](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)

- [Support of adaptive icons in PWAs with maskable icons](https://web.dev/maskable-icon/?utm_source=devtools)


## Full Template
````json
{
  "name": "Nuxt PWA Template",
    "short_name": "Nuxt PWA", // Name of app at devide when installed.
    "description": "A awesome PWA template build with Nuxt",
    "start_url": "http://localhost:3000/",
    "display": "standalone",
    "orientation": "portrait",
    "background_color": "#121212",
    "theme_color": "#121212",
    "scope": "http://localhost:3000/", // Routes scope. Other urls will land the browser.
  "icons": [{
    "src": "images/touch/homescreen48.png",
    "sizes": "48x48",
    "type": "image/png"
  }, {
    "src": "images/touch/homescreen72.png",
    "sizes": "72x72",
    "type": "image/png"
  }, {
    "src": "images/touch/homescreen96.png",
    "sizes": "96x96",
    "type": "image/png"
  }, {
    "src": "images/touch/homescreen144.png",
    "sizes": "144x144",
    "type": "image/png"
  }, {
    "src": "images/touch/homescreen168.png",
    "sizes": "168x168",
    "type": "image/png"
  }, {
    "src": "images/touch/homescreen192.png",
    "sizes": "192x192",
    "type": "image/png"
  }],
  "related_applications": [{
    "platform": "web"
  }, {
    "platform": "play",
    "url": "https://play.google.com/store/apps/details?id=com.google.samples.apps.iosched"
  }],
  "screenshots" : [
    // These images are intended to be used by progressive web app stores.
  {
    "src": "screenshot1.webp",
    "sizes": "1280x720",
    "type": "image/webp",
    "platform": "wide",
    "label": "Homescreen of Awesome App"
  },
  {
    "src": "screenshot2.webp",
    "sizes": "1280x720",
    "type": "image/webp",
    "platform": "wide",
    "label": "List of Awesome Resources available in Awesome App"
  }

}
````

---

### Keys

[List of manifest.json keys](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json#list_of_manifest.json_keys)

## Options

### `background_color`
Defines the desired background color for the application. This value echoes what is defined in the application's style sheet, but can be used by browsers to paint an app's background color if the manifest is available before the style sheet has been loaded. This smoothes the transition between launching an app and loading the app's content.

````json
"background_color": "red"
````

### `description`

Provides an overview of what the app does.

````json
"description": "The app that helps you find the best food in town!"
````
