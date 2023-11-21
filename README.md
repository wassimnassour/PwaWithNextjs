# How To Config PWA in your next app

## Manifest config details

- display: this can be standalone or minimal ui or full screen
  ![Difference between standalone or minimal ui or full screen](/public/pwa-phone-size.png "Difference between standalone or minimal ui or full screen")

- start_url :The "start_url" property specifies the URL that should be loaded when the user launches the web application. It is also used as the default URL when the app is added to the home screen. The value is a string representing the URL. For example:

- scope: The "scope" property defines the navigation scope of the web application. It determines which pages are within the app's scope and can be navigated to without leaving the app experience . like if you want to access singing with google it will open new tab like browser in your app

- icons : so about icons you should know the supported sizes and types
  - recommendation Sizes :
  - at least : 192X192
  - 384x384 ,1024x1024
  - 🔴 the icons is not working on ios you should add new meta tag to support ios
    <link rel="apple-touch-icon" sizes="190x190" href="/path/to/your/icon.png">
- shortcuts: allow users to go directly into a specific action or page by long-pressing the app logo.

## things you should be aware of

- when you build PWA,the user can start selecting things like the text in button or titles , so you want to give the best experience , you can add user-select:none and -webkit-user-select:none to your tag or class to make sure that user can't select this text

- when you use standalone if there’s any button or anything in the safe area , you can’t access cuz the the phone is using it we can use media with display mode

  ```css
  @media (display-mode: standalone) {
    padding-bottom: 32px;
  }
  ```

  you can also use [env](https://developer.mozilla.org/en-US/docs/Web/CSS/env) from css to fill the screen when you are working with rotation screen

- To make sure your Icon will fit and look exactly as you want without any white background or anything , check this
  [https://web.dev/articles/maskable-icon](https://web.dev/articles/maskable-icon)

## offline Support

- you can add fallback offline page visit this [https://github.com/shadowwalker/next-pwa/tree/master/examples/offline-fallback-v2](https://github.com/shadowwalker/next-pwa/tree/master/examples/offline-fallback-v2)

- also you can register service worker and start cashing the resourses , visit this [https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
