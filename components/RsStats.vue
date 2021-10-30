<template>
    <div class="rs-stats">
        <!-- <v-card dark>
            <v-card-title class="rs-card-title">
                <v-icon size="32" class="mt-n3">mdi-chart-box</v-icon>
                <p class="headline mx-2">Stats</p>
            </v-card-title>
            <v-card-text class="rs-card-text pa-1"> -->
        <RsCard title="Stats" icon="mdi-chart-box">
                <v-list>
                    <v-list-item>
                        <v-list-item-icon><v-icon>mdi-file-image</v-icon></v-list-item-icon>
                        <v-list-item-content>{{ stats.images }} images</v-list-item-content>
                    </v-list-item>
                     <v-list-item>
                        <v-list-item-icon><v-icon>mdi-comment</v-icon></v-list-item-icon>
                        <v-list-item-content>{{ stats.comments }} comments</v-list-item-content>
                    </v-list-item>
                     <v-list-item>
                        <v-list-item-icon><v-icon>mdi-eye-settings</v-icon></v-list-item-icon>
                        <v-list-item-content>{{ stats.views }} views</v-list-item-content>
                    </v-list-item>
                     <v-list-item>
                        <v-list-item-icon><v-icon>mdi-thumb-up</v-icon></v-list-item-icon>
                        <v-list-item-content>{{ stats.likes }} likes</v-list-item-content>
                    </v-list-item>
                </v-list>
        </RsCard>
    </div>
</template>

<script>
export default {
    data(){
        return{
            stats:{
                images:0,
                comments:0,
                views:0,
                likes:0,
            },
            onFetch: undefined,
        }
    },
    async beforeMount(){
        this.onFetch = setInterval( async ()=>{
            await this.loadStats()
        }, 2000)
    },
    beforeDestroy(){
        clearInterval(this.onFetch);
    },
    methods:{
        async loadStats(){
            try{
                const res = await fetch('http://localhost:4500/api/post/stats');
                const data = res.json();
                if(data.error){
                    console.log(data.error);
                    return;
                }
                this.stats = data;
            }catch(err){
                console.log(err);
            }
        }
    }
}
</script>


