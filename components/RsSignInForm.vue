<template>
    <div class="rs-sign-in-form mt-4">
        <v-row>
            <v-col class="col-md-6 offset-md-3">
                <v-card>
                    <v-card-title class="justify-center">Sign In</v-card-title>
                    <v-card-text>
                        <v-text-field placeholder="Email" type="email" outlined v-model="email"></v-text-field>
                        <v-text-field placeholder="Password" type="password" outlined v-model="password"></v-text-field>
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
            email:'',
            password:'',
        }
    },
    methods:{
        async submit(){
            try{
                if(this.email.length < 4 || this.password.length < 4){
                    alert('Campos requeridos');
                    return;
                }
                const body = JSON.stringify({
                    email: this.email,
                    password: this.password,
                })
                const res = await fetch('http://localhost:4500/api/user/signIn',{
                    method:'post',
                    headers:{
                        'Content-Type': 'application/json',
                    },
                    body,
                })
                const data = await res.json();
                if(data.error){
                    alert(data.error);
                    return;
                }
                localStorage.setItem('email', data.email);
                localStorage.setItem('avatar', data.avatar);
                this.$store.dispatch('user/saveToken', data.token);
            }catch(err){
                alert(err.message);
            }
        }
    }
}
</script>