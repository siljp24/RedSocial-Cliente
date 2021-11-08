<template>
    <div class="rs-comment-item">
        <v-row>
            <v-col cols="4">
                <v-img aspect-ratio="1" :src="image" v-on:click="onClick()"></v-img>
            </v-col>
            <v-col cols="8">
                <p class="font-weight-black">{{email}}</p>
                <p>{{comment}}</p>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    props:{
        image:{
            type: String,
            required:true,
        },
        email:{
            type: String,
            required:true,
        },
        comment:{
            type: String,
            required:true,
        },
        postId:{
            type: String,
            required:true,
        }
    },
    methods:{
        onClick(){
            this.$router.push(`/details/${this.postId}`);
        }
    }
}
</script>