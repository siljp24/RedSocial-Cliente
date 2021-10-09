<template>
    <div class="rs-all-comments">
        <RsCard :header="false">
            <div class="rs-all-comments-container">
                <v-row v-for="(obj, index) in comments" :key="obj.id">
                    <v-col cols="4" class="d-flex justify-center">
                        <v-avatar size="110px">
                            <v-img :src="obj.avatar" />
                        </v-avatar>
                    </v-col>
                    <v-col cols="8">
                        <p class="font-weight-black">{{ obj.title }}</p>
                        <p>{{ obj.comment }}</p>
                    </v-col>
                    <v-col cols="12" v-if="index !== comments.length - 1">
                        <v-divider></v-divider>
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
            comments:[
                {
                    id:1,
                    title:"title 1",
                    avatar: "https://i.picsum.photos/id/1011/5472/3648.jpg?hmac=Koo9845x2akkVzVFX3xxAc9BCkeGYA9VRVfLE4f0Zzk",
                    comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut iaculis v",
                },
                {
                    id:2,
                    title:"title 2",
                    avatar: "https://i.picsum.photos/id/1005/5760/3840.jpg?hmac=2acSJCOwz9q_dKtDZdSB-OIK1HUcwBeXco_RMMTUgfY",
                    comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut iaculis v",
                },
                {
                    id:3,
                    title:"title 3",
                    avatar: "https://i.picsum.photos/id/1027/2848/4272.jpg?hmac=EAR-f6uEqI1iZJjB6-NzoZTnmaX0oI0th3z8Y78UpKM",
                    comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut iaculis v",
                }
            ]
        }
    }
}
</script>