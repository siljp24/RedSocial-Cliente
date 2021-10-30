<template>
    <div class="rs-details id">
        <RsImageDetails :post="post" comments=""/>
        <RsComment class="mt-4"/>
        <RsAllComments class="mt-4"/>
    </div>
</template>

<script>
export default {
    async asyncData(ctx){
        try{
            //views
            // const res = await fetch('http://localhost:4500/api/post/view',{
            //     method:'post',
            //     headers:{
            //         'Content-Type': 'application/json',
            //     }, 
            //     body: JSON.stringify({
            //         postId:ctx.params.id,
            //     })
            // })
            const res = await fetch(`http://localhost:4500/api/post/details/${ctx.params.id}`)
            const data = await res.json();
            return{
                post: data.post,
                comments: data.comments,
                onFetch: undefined,
            }
        }catch(err){
            console.log(err.message);
            ctx.redirect('/home');
        }
    }, 
    mounted(){
        this.onFetch = setInterval(async ()=>{
            await this.loadDetails()
        }, 1000)
    },
    beforeDestroy(){
        clearInterval(this.onFetch)
    },
    methods:{
        async loadDetails(ctx){
            try{
                const res = await fetch(`http://localhost:4500/api/post/details/${ctx.params.id}`)
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