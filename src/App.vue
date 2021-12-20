<template>
  <div class="bg-red-400 w-full h-screen flex items-center justify-center">
    <img
      class="w-1/2"
      :src="require(`./assets/images/${imageSrc}`)"
      :alt="imageSrc"
      @click="changeOnClick"
    />
  </div>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    imageSrc: 'chat-lunette.jpeg',
  }),

  methods: {
    changeOnClick() {
      const imageList = [
        'chat-lunette.jpeg',
        'mongolfiere.jpg',
        'orange.jpeg',
        'papillon.jpg',
      ]

      const randomIndex = Math.floor(Math.random() * imageList.length)

      if (imageList[randomIndex] === this.imageSrc) {
        this.changeOnClick()
      } else {
        this.imageSrc = imageList[randomIndex]
      }
    },
  },
}
</script>
