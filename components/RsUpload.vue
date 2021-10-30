<template>
    <div class="rs-upload">
        <RsCard title="Upload" icon="mdi-cloud-upload">
            <div class="rs-upload-container">
                   <v-file-input outlined prepend-icon="" placeholder="File" v-model="image"></v-file-input>
                   <v-text-field outlined name="title" placeholder=" Image Title" v-model="title"></v-text-field>
                   <v-textarea outlined name="description" placeholder="Description" v-model="description"></v-textarea>
                   <div class="rs-btn-container d-flex justify-end">
                        <v-btn color="success" type="submit" v-on:click="submit">Submit</v-btn>
                   </div>
            </div>
        </RsCard>
    </div>
</template>

<script>
export default {
    data(){
        return{
            image:undefined,
            title:'',
            description:'',
        }
    },
    methods:{
        async submit(){
            try{
                const formData = new FormData();
                formData.enctype = 'multipart/form-data';
                formData.append('image', this.image);
                formData.append('title', this.title);
                formData.append('description', this.description);
                const token = localStorage.getItem('token');
                const res = await fetch('http://localhost:4500/api/post/upload', {
                    method:'post',
                    headers:{
                        token: token,
                    },
                    body: formData,
                        
                })
                const data = await res.json();
                if(data.error){
                    console.log(data.error);
                    return
                }
            }catch(err){
                console.log(err.message);
            }
        }
    }
}
</script>