<template>
    <div v-if="video" class="col-md-8">
        <div class="embed-responsive embed-responsive-16by9">
      
            <iframe :src="VideoPlay"
                
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen
                class="embed-responsive-item"
                ></iframe>

            </div>
            <h5 class="my-3">{{ video.snippet.title }}</h5>
            <p class="my-3 px-3">{{ video.snippet.description }}</p>
    </div>
    
</template>

<script>
export default {
    name: 'VideoDetail',
    props: ['video'],
    computed: {
        VideoPlay() {
            const {videoId} = this.video.id;
            return `https://www.youtube.com/embed/${videoId}`;
        }
    }
}
</script>