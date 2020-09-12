<template>
  <li class="list-group-item" @click="onVideoSelect">
    <div class="media">
      <img class="mr-3" :src="thumbnailURL">

      <div class="media-body">
        <h5 class="mt-0">{{ title }}</h5>
<!--        {{ description }}-->
      </div>
    </div>

  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: ['video'],
  computed: {
    thumbnailURL() {
      return this.video.snippet.thumbnails.default.url;
    },
    title() {
      return this.video.snippet.title
    },
    description() {
      return this.video.snippet.description
    },
  },
  methods: {
    onVideoSelect() {
      this.$emit('videoSelect', this.video);
    }
  }
}
</script>

<style scoped>
li {
  cursor: pointer;
}

li:hover {
  background-color: #eee;
}
</style>