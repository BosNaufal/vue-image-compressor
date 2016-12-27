# Vue Image Compressor
[Vue](http://vuejs.org) Component To Compress Image Files. It's based on [cpol-image](https://beta.webcomponents.org/element/3mp3ri0r/cpol-image) and [others references](#credits)

[DEMO](https://bosnaufal.github.io/vue-image-compressor)


## Install
You can import [vue-image-compressor.vue](./dist/vue-image-compressor.js) to your vue component file like [this](./src/js/components/app.vue) and process it with your preprocessor.

You can install it via NPM
```bash
npm install vue-image-compressor
```

Or Just put it after Vue JS~
```html
<script src="https://vuejs.org/js/vue.min.js"></script>
<script src="./dist/vue-image-compressor.js"></script>
```


## Import Module
```javascript
import imageCompressor from 'vue-image-compressor'
// Or
var imageCompressor = require('vue-image-compressor');
```

## Usage
```html
<template>

  <image-compressor
    :done="getFiles"
    :scale="scale"
    :quality="quality">
  </image-compressor>

</template>


<script>

  import imageCompressor from 'vue-image-compressor';

  export default {

    components: { imageCompressor },

    methods: {
      getFiles(obj){
        console.log(obj);
      }
    }
  };

</script>
```

## Props
#### done (Function)
Callback after Compress the image. It will pass original file and compressed file and also the canvas element. The object pretty complete with blob and base64 and other needed information.

#### scale (Number)
The percentage of image scaling it starts from 1 to 100.

#### quality (Number)
The percentage of image quality it starts from 1 to 100.


## Credits
- [https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL)
- [https://davidwalsh.name/convert-canvas-image](https://davidwalsh.name/convert-canvas-image)
- [https://beta.webcomponents.org/element/3mp3ri0r/cpol-image](https://beta.webcomponents.org/element/3mp3ri0r/cpol-image)

## Thank You for Making this useful~

## Let's talk about some projects with me
Just Contact Me At:
- Email: [bosnaufalemail@gmail.com](mailto:bosnaufalemail@gmail.com)
- Skype Id: bosnaufal254
- twitter: [@BosNaufal](https://twitter.com/BosNaufal)

## License
[MIT](http://opensource.org/licenses/MIT)
Copyright (c) 2016 - forever Naufal Rabbani
