<template>
    <div class="rs-latest-comments">
        <RsCard title="Latest Comments" icon="mdi-comment">
            <RsCommenItem 
            v-for="comment in comments" 
            :key="comment.comment._id" 
            :image="comment.post.image"
            :email="comment.user.email"
            :comment="comment.comment.description"
            :postId="comment.post._id"/>
        </RsCard>
    </div>
</template>

<script>
export default {
    data(){
        return{
            comments:[],
        }
    },
    async beforeMount(){
        await this.loadComments()
    },
    methods:{
        async loadComments(){
            try{
                const res = await fetch('http://localhost:4500/api/comment/lastestComments');
                const data = await res.json();
                if(data.error){
                    console.log(data.error);
                    return;
                }
                for(const comment of data.comments){
                    this.comments.push(comment);
                }
            }catch(err){
                console.log(err);
            }
        }
    }
}
</script>