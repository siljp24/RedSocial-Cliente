<template>
    <div class="rs-details id">
        <RsImageDetails :post="post" v-if="post" :isOwner="isOwner"/>
        <RsComment class="mt-4" v-if="showComments"/>
        <RsAllComments class="mt-4" :comments="comments" />
    </div>
</template>

<script>
export default {
    async asyncData(ctx){
        try{
            const body = JSON.stringify({
                postId: ctx.params.id,
            }) 
            await fetch('http://localhost:4500/api/post/view',{
                method:'post',
                headers:{
                    'Content-Type': 'application/json',
                },
                body,
            })
            const token = ctx.store.state.user.token;
            const res = await fetch(`http://localhost:4500/api/post/details/${ctx.params.id}`,{
                headers:{
                    'Content-Type': 'application/json',
                    ...(token ? { token } : {}),
                }
            });
            const data = await res.json();
            if(data.error || !data.post){
                console.log(data.error);
                ctx.redirect('/home');
            }
            const post = data.post;
            const comments = data.comments;
            const isOwner = data.isOwner;
            return{
                post,
                comments,
                isOwner,
                onFetch: undefined,

            }
        }catch(err){
            console.log(err.message);
            ctx.redirect('/home');
        }
    }, 
    computed:{
        showComments(){
            return this.$store.state.user.token;
        }
    },
    mounted(){
        this.onFetch = setInterval(async ()=>{
            await this.loadDetails()
        }, 1000)
    },
    beforeDestroy(){
        clearInterval(this.onFetch);
    },
    methods:{
        async loadDetails(ctx){
            try{
                const token = this.$store.state.user.token;
                const res = await fetch(`http://localhost:4500/api/post/details/${this.post._id}`,{
                    headers:{
                        'Content-Type': 'application/json',
                        ...(token ? { token } : {}),
                    },
                })
                const data = await res.json();
                this.post= data.post;
                this.comments= data.comments;
            }catch(err){
                console.log(err.message);
                this.$router.push('/home');
            }
        }
    }
}
</script>