<template>
    <div class="rs-sign-up">
       <RsSignUpForm />
    </div>
</template>

<script>
export default {
    layout: 'auth',
    data(){
        return{
            isValid: true,
        }
    },
    asyncData(ctx){
        if(ctx?.store?.state?.user?.token){
            ctx.redirect('/home');
        }
    },
    created (){
        if(process.client){
            const token = localStorage.getItem('token');
            if(token){
                this.$router.push('/home');
            }
        }
    },
    computed:{
        token(){
            return this.$store.state.user.token;
        }
    }
}
</script>