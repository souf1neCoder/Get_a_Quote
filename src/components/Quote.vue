<template>
  <section class="quote">
    <div class="quote-content">
      <div class="tag">
        <h4>#{{ quotes.tag }}</h4>
      </div>
      <blockquote>
        <i class="fas fa-quote-left"></i> {{ quotes.text }}
        <i class="fas fa-quote-right"></i> -- <i class="aut">{{ quotes.author }}</i>
      </blockquote>
    </div>
  </section>
</template>

<script>
export default {
  props: ["quotes"],
};
</script>

<style scoped>
.quote {
  background: var(--dark-color);
  padding: 40px;
  color: #fff;
  width: 50%;
  max-width: 50%;
}
@media only screen and (max-width:500px){
    .quote{
        width: 90%;
        max-width: 90%;
    }
    blockquote{
        font-size: 1.1rem;
        letter-spacing: .5px;
    }
    .aut{
        font-size: 1rem;
    }
}
h4{
    letter-spacing: 1.5px;
    margin: 15px 0;
}
blockquote{
    letter-spacing: 1px;
    font-size: 1.33rem;
}
.aut{
    font-size: 1.1rem;
}

</style>
