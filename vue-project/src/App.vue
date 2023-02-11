

<template>
  <div class="container">
    
  <SearchBar @termChange="onTermChange" />
  <div class="row">
    
    <VideoDetail :video="SelectedVideo"/>
    <VideoList @VideoChange="onVideoChange" :videos="videos"/>
  </div>
  
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/Searchbar.vue';
import VideoList from './components/VideoList.vue';
import VideoDetail from './components/VideoDetail.vue';

const API_KEY = 'AIzaSyBozG3VlI2psbUPAFtXLvQJIR2NpWKHLL0';

export default {
  name: 'App',
  data() {
    return {
      videos: [],
      SelectedVideo: null,

    };
  },

  components: {
    SearchBar,
    VideoList,
    
    VideoDetail,
    
  },
  methods: {
    onVideoChange(video) {
      
      this.SelectedVideo = video;
      
    },

    onTermChange: function (SearchChange) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: SearchChange,
        }
      }).then(
        response => {
          this.videos = response.data.items
        }
      )
    }
  }
}
</script>

<style scoped>

</style>
