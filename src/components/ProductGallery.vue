<template>
  <div class="image-container">

    <img src="../assets/image-product-1.jpg" alt="">

    <div class="gallery-buttons">

      <button  @click="previousImage" class="gallery-button">
        <img src="../assets/icon-previous.svg" alt="" class="icon-next">
      </button>

      <button @click="nextImage" class="gallery-button">
        <img src="../assets/icon-next.svg" alt="" class="icon-next">
      </button>

    </div>
  </div>
</template>
<script>


export default {
  name: "ProductGallery",
  methods: {
    nextImage() {
      console.log('next image')
    },
    previousImage() {
      console.log('prev image')
    }
  }

}
</script>

<style scoped lang="scss">
.image-container {
  position: relative;
}

.gallery-buttons {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 15px;
  right: 15px;


}

.gallery-button {
  padding: 15px 15px;
  border-radius: 50%;
  background-color: #ffffff;
  display: inline-flex;
  align-items: center;
  border: none;
}

img {
  width: 100%;
}


</style>
