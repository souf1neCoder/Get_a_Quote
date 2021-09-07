<template>
  <header>
      <div class="logo">
          <h1><i class="fas fa-quote-left"></i> <span>{{ title }}</span></h1>
      </div>
  </header>
</template>

<script>
export default {
    props:['title']
}
</script>

<style scoped>
header{
    width:100%;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: var(--second-color);
}
.logo{
    color: #fff;
    cursor: pointer;
}
h1 span{
    letter-spacing: 3px;
}
</style>