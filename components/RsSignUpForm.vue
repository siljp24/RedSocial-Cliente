<template>
    <div class="rs-sign-up-form mt-4">
        <v-row>
            <v-col class="col-md-6 offset-md-3">
                <v-card>
                    <v-card-title class="justify-center">Sign Up</v-card-title>
                    <v-card-text>
                        <v-file-input v-model="avatar" placeholder="Avatar" outlined prepend-icon="" name="avatar"></v-file-input>
                        <v-text-field v-model="email" placeholder="Email" type="email" outlined name="email"></v-text-field>
                        <v-text-field v-model="password" placeholder="Password" type="password" outlined name="password"></v-text-field>
                        <v-text-field v-model="password2" placeholder="Repeat Password" type="password" outlined name="password2"></v-text-field>
                        <v-btn color="success" block v-on:click="submit">Submit</v-btn>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
        
        
    </div>
</template>

<script>
export default {
    data(){
        return{
            avatar:undefined,
            email:'',
            password:'',
            password2:'',
        }
    },
    methods:{
        async submit(){
            if(this.password !== this.password2){
                alert('Contraseñas diferentes');
                return;
            };
            const formData = new FormData();
            formData.enctype = 'multipart/form-data';
            formData.append('avatar', this.avatar);
            formData.append('email', this.email);
            formData.append('password', this.password);
            try{
                const res = await fetch('http://localhost:4500/api/user/signUp',{
                    method: 'POST',
                    body: formData,
                })
                const data = await res.json();
                if(data.error){
                    alert(data.error);
                    return;
                }else{
                    this.$router.push('/sign-in');
                }
            }catch(err){
                alert(err.message);
            }

        }
    }
}
</script>