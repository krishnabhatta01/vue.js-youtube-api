<template>
<div>
    
       <!--  <img :src="VideoThumbnail" alt="thumbnail">
        {{ video.snippet.title }} -->

        <div class="cardSection card mb-1" @click="onVideoSelect">
            <div class="row g-0">
                <div class="col-md-4">
                    <img :src="VideoThumbnail" class="img-fluid d-block my-auto" alt="thumbnail">
                </div>
                <div class="col-md-8">
                    <div class="card-body">
                        <h7 class="card-text">{{ video.snippet.title }}</h7>
                        
                    </div>
                </div>
            </div>
        </div>

    
</div>
</template>


<script>
export default{
    name: 'VideoListItem',
    props: ['video'],
    computed: {
        VideoThumbnail() {
            return this.video.snippet.thumbnails.default.url;
        }
    },
    methods: {
        onVideoSelect() {
            return this.$emit('VideoSelect',this.video);
        }
    }
}
</script>

<style scoped>
.cardSection{
    
    cursor:pointer;
}

.cardSection:hover{
    background-color: #eee;
}
</style>