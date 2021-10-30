<template>
    <div class="rs-image-details">
        <RsCard :title="post.title" remove>
            <div class="rs-image-details-container">
                <v-img :src="post.image" height="400px"/>
                <div class="rs-image-details-container-description">
                    <p class="headline font-weight-black">{{ post.title }}</p>
                    <p>{{ post.description }}</p>
                </div>
                <div class="rs-image-details-container-info d-flex">
                    <div class="rs-image-details-container-info-start d-flex justify-start">
                        <v-btn color="success" v-on:click="onLike">
                            <v-icon class="mx-2">mdi-thumb-up</v-icon>
                            Like
                        </v-btn>
                        <div class="mx-12">
                            <v-icon class=" d-flex justify-center">mdi-cards-heart</v-icon>
                            <p>{{ post.likes }}</p>
                        </div>
                        <div class="mx-12">
                            <v-icon class="d-flex justify-center">mdi-eye-settings</v-icon>
                            <p>{{ post.views }}</p>
                        </div>
                    </div>
                    <v-spacer></v-spacer>
                    <div class="rs-image-details-container-info-end">
                        <p>08/10/2021</p>
                    </div> 
                </div>
            </div>
        </RsCard>
    </div>
</template>

<script>
export default {
    props:{
        post:{
            type:Object,
            required:true,
        }
    },
    data(){
        return{
            title:"Image title",
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi tempus faucibus ipsum, ac volutpat tellus molestie id. Aliquam elementum accumsan nisi, imperdiet finibus dolor sagittis id. Donec congue justo convallis.'
        }
    },
    methods:{
        async onLike(){
            try{
                const body = JSON.stringify({
                    postId: this.post._id
                })
                const res = await fetch('http://localhost:4500/api/post/like',{
                    method:'post',
                    headers:{
                        'Content-Type': 'application/json',
                    },
                    body,
                })
                const data = await res.json();
                if(data.error){
                    console.log(data.error);
                }
            }catch(err){
                console.log(err.message);
            }
        }
    }
}
</script>