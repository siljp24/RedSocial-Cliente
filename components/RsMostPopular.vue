<template>
    <div class="rs-most-popular">
        <RsCard title="Most Popular" icon="mdi-camera-image">
        <div class="rs-images-container">
            <v-row class="pa-2">
                <v-col cols="6" v-for="image in images" :key="image.id" class="-rs-images-container-item">
                    <v-img :src="image.url"></v-img>
                </v-col>
            </v-row>
    
        </div>
        </RsCard>
    </div>
</template>

<script>
export default {
    data(){
        return{
            images:[
                {
                    id:1,
                    url:'https://picsum.photos/id/237/200/300'
                },
                {
                    id:2,
                    url:'https://picsum.photos/seed/picsum/200/300'
                },
                {
                    id:3,
                    url:'https://picsum.photos/200/300?grayscale'
                },
                {
                    id:4,
                    url:'https://picsum.photos/id/237/200/300'
                },
            ]
        }
    }
}
</script>