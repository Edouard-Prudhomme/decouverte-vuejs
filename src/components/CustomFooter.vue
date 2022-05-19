<template>
  <footer class="footer">
    <a href="/mentions-legales">Mentions légales</a>
    <a href="/contact">Contact</a>
    {{ today }}
  </footer>    
</template>

<script>
export default {
  props: ["today"]
}
</script>

<style lang="scss">
.footer {
  background-color: black;  
  padding: 1rem;
  color: white;

  a {
    color: white;
  }
}
</style>