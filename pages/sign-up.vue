<template>
    <div class="rs-sign-up">
       <RsSignUpForm />
    </div>
</template>

<script>
export default {
    layout: 'auth',
    created (){
        const token = localStorage.getItem('token');
        if(token){
            this.$router.push('/home');
        }
    }
}
</script>