<template>
    <div class="rs-sign-in">
        <RsSignInForm />
    </div>
</template>

<script>
export default {
    layout: 'auth',
    mounted (){
        const token = localStorage.getItem('token');
        if(token){
            this.$router.push('/home');
        }
    }
}
</script>