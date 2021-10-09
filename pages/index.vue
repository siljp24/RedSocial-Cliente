<template>
  <div class="rs-index">
    <p>Index</p>
  </div>
</template>

<script>
export default {
  asyncData(ctx){
    ctx.redirect('/home');
  }
}
</script>
