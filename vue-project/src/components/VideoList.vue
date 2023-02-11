<template>
<div class="list-group mx-auto col-4">
    <VideoListItem v-for="video in videos" :key="video.etag" :video="video" @VideoSelect="onVideoChange"/>
</div>
</template>

<script>
import VideoListItem from './VideoListItem.vue';
export default {
    name: 'VideoList',
    props: ['videos'],
    components: {
        VideoListItem
    },
    methods: {
        onVideoChange(video) {
             this.$emit('VideoChange',video)
        }
    }
}
</script>

<style>

</style>