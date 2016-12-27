
<template>
  <div align="center">

    <h1>Client Side Image Compressor</h1>
    <p>Try To Upload Some Image~</p>

    <button class="upload-button button" type="button" @click="upload">Upload</button>
    <image-compressor class="compressor" :done="getFiles" :scale="scale" :quality="quality" ref="compressor"></image-compressor>

    <div class="checkbox">
      <input type="checkbox" v-model="originalSize">
      <span>Responsive Image?</span>
    </div>

    <div class="input-group">
      <label>Image Scale</label>
      <input type="number" v-model="scale">
    </div>

    <div class="input-group">
      <label>Image Quality</label>
      <input type="number" v-model="quality">
    </div>

    <div class="image-info" v-if="img">
      <b>Before: </b>
      <span>{{ original.size }}</span>
      <span class="separator"> | </span>
      <b>After: </b>
      <span>{{ compressed.size }}</span>
    </div>

    <div class="text-center" v-if="img">
      <img v-if="img" src="" alt="" :style="{ maxWidth: originalSize ? '100%' : null }" :src="img">
      <a :href="img" class="button" target="_blank">Download</a>
    </div>

  </div>

</template>

<script>

  import imageCompressor from './vue-image-compressor.vue';

  export default {

    data(){
      return{
        img: "",
        scale: 100,
        quality: 50,
        originalSize: true,

        original: {},
        compressed: {},
      }
    },

    components: { imageCompressor },

    methods: {
      upload () {
        let compressor = this.$refs.compressor.$el
        compressor.click()
      },

      getFiles(obj){
        this.img = obj.compressed.blob
        this.original = obj.original
        this.compressed = obj.compressed
      },
    }
  };

</script>


<style>
  body {
    font-family: Roboto;
  }

  p {
    margin-bottom: 25px;
  }

  .image-info {
    margin: 15px 0;
  }

  .separator {
    margin: 0 5px;
  }

  input {
    width: 75%;
    display: block;
    padding: 5px;
    text-align: center;
    margin-bottom: 10px;
    max-width: 250px;
    border: 2px solid #DDD;
  }

  input:focus {
    border: 2px solid blue;
  }

  .compressor {
    display: none;
  }

  .button {
    display: inline-block;
    border-radius: 3px;
    background: #1A237E;
    color: white;
    padding: 7px 15px;
    border: 0;
    box-shadow: 0px 2px 4px 1px rgba(0,0,0,.4);
    margin-bottom: 10px;
    cursor: pointer;
    outline: none;
    text-decoration: none;
  }

  label {
    margin-bottom: 10px;
    display: block;
  }

  .input-group {
    margin: 25px 0;
  }

  .checkbox {
    margin: 15px 0 20px;
    background: #EEE;
    padding: 10px 0;
  }

  .checkbox input {
    width: auto;
    display: inline-block;
  }

  img {
    margin: 0 auto;
    display: block;
  }

  a {
    margin: 25px 0 75px;
  }
</style>
