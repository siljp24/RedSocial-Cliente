<template>
    <div class="rs-layout-default">
        <v-app>
            <RsAppBar />
            <v-main>
                <v-container>
                    <v-row>
                        <v-col :cols="leftColumn">
                            <Nuxt />
                        </v-col>
                        <v-col :cols="rightColumn">
                            <RsStats />
                            <RsMostPopular class="mt-4"/>
                            <RsLatestComments class="mt-4"/>
                        </v-col>
                    </v-row>
                </v-container> 
            </v-main>
        </v-app>
    </div>
</template>

<script>
export default {
    beforeMount(){
        const token = localStorage.getItem('token');
        if(token){
            this.$store.commit('user/setToken', token);
        }
    },
    watch:{
        '$store.state.user.token'(value){
            if(!value){
                this.$router.push('/sign-in');
            }
        }
    },
    computed:{
        leftColumn(){
            const value = this.$vuetify.breakpoint.name;
            if(value === 'xs' || value === 'sm'){
                return 12;
            }
            return 8;
        },
        rightColumn(){
            const value = this.$vuetify.breakpoint.name;
            if(value === 'xs' || value === 'sm'){
                return 12;
            }
            return 4;
        }
    }
}
</script>

