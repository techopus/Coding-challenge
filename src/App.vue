
<template>
    <h1> Images</h1>
      <!-- {{images}} -->

  <div class="images_container">
  <div v-for="(image, index)  in images"  :key="index" class="image">
    <div class="image_sizer">
      <img :src="`${image.download_url}`"   >
    </div>
    <p>{{image.author}}</p> 
  </div>
  </div>
  
</template>

<script lang="ts">
import { anyTypeAnnotation } from '@babel/types'
import { defineComponent } from 'vue' 

interface Image {
  id: number,
  author: string,
  width: number,
  height: number,
  url: string,
  download_url: string
}

export default defineComponent({
  data(){
    return{
      images : [] as Image[]
    }
  },
  mounted(){
    console.log("test")
    fetch('https://picsum.photos/v2/list?page=2&limit=12')
      .then(res => res.json())
      .then(data => {
            let images:Image[] = []
            for (let i = 0; i < data.length; i++) {
              let image:Image = {
                  id: data[i].id,
                  author: data[i].author,
                  width: data[i].width,
                  height: data[i]. height,
                  url: data[i].url,
                  download_url: data[i].download_url
              }

              images.push(image)
            }

            this.images = images;
      })
      .catch(err => console.log(err.message))
  }
})

</script>

<style>
#app {
font-family: Avenir, Helvetica, Arial, sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
text-align: center;
color: #2c3e50;
margin-top: 60px;
}

.images_container {
  margin-left: 3%;
  width: 100%;
  display: grid;
  grid-template-columns: 30% 30% 30%;
  column-gap: 3%;
  row-gap: 3%;
  justify-items: center;
}

img {
  width: 100%;
}

.image_sizer {
  height: 15vw;
  overflow: hidden;
}

@media  screen and (max-width: 600px) {
  .images_container {
  margin-left: 10%;
  width: 100%;
  display: grid;
  grid-template-columns: 80%;
  column-gap: 3%;
}

img {
  width: 100%;
  height: fit-content;
}

.image_sizer {
  height: initial;
  overflow: hidden;
}
}

</style>
