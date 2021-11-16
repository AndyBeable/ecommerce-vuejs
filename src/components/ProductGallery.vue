<template>
  <div class="image-container">
    <img :src="images[index]" alt="" class="product-image">
<!--    <img src="../assets/one.jpg" alt="">-->

    <div class="gallery-buttons">

      <button  @click="previousImage" class="gallery-button">
        <img src="../assets/icon-previous.svg" alt="">
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
  props: {
    thumbnail: {
      type: String,
      required: true
    },
    images: {
      type: Array,
      required: true
    }

  },
  data() {
    return {
      isVisible: false,
      index: 0
    }
  },
  methods: {
    // showGallery() {
    //   this.isVisible = true
    // },
    // hideGallery() {
    //   this.isVisible = false
    //   this.index = 0;
    // },
    hasNextImage() {
      return this.index + 1 < this.images.length
    },
    hasPreviousImage() {
      return this.index - 1 >= 0;
    },
    nextImage() {
      if(this.hasNextImage()) {
        this.index += 1;
      }
    },
    previousImage() {
      if(this.hasPreviousImage()) {
        this.index -=1;
      }
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
  background-color: var(--white);
  display: inline-flex;
  align-items: center;
  border: none;
}

//img {
//  width: 100%;
//}
</style>
