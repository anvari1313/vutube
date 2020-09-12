<template>
  <div class="container">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <div class="row">
      <VideoDetail :video="selectedVideo"/>
      <VideoList v-bind:videos="videos" @videoSelect="onVideoSelect"></VideoList>
    </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetail from "./components/VideoDetail";

import axios from 'axios';

const API_KEY = process.env.VUE_APP_GOOGLE_API_KEY;

export default {
  name: "App",
  data() {
    return {
      videos: [],
      selectedVideo: null,
    }
  },
  components: {
    SearchBar,
    VideoDetail,
    VideoList,
  },
  methods: {
    onVideoSelect(video) {
      this.selectedVideo = video;
    },
    onTermChange(term) {
      let config = {
        method: "get",
        url:
            "https://www.googleapis.com/youtube/v3/search",
        headers: {},
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: term
        }
      };

      axios(config)
          .then(res => {
            this.videos = res.data.items
          })
          .catch(console.error);
    },
  },
};
</script>