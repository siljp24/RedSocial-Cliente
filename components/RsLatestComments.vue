<template>
    <div class="rs-latest-comments">
        <RsCard title="Latest Comments" icon="mdi-comment">
            <RsCommenItem 
            v-for="comment in comments" 
            :key="comment.id" 
            :image="comment.image"
            :email="comment.email"
            :comment="comment.comment"/>
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
                    image:'https://picsum.photos/200',
                    email:'pepe@gmail.com',
                    comment:'orem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam posuere.',
                },
                {
                    id:2,
                    image:'https://picsum.photos/200/300',
                    email:'jose@gmail.com',
                    comment:'orem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam posuere.',
                },
                {
                    id:3,
                    image:'https://picsum.photos/id/237/200/300',
                    email:'maria@gmail.com',
                    comment:'orem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam posuere.',
                },
                {
                    id:4,
                    image:'https://picsum.photos/seed/picsum/200/300',
                    email:'ana@gmail.com',
                    comment:'orem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam posuere.',
                },
            ]
        }
    }
}
</script>