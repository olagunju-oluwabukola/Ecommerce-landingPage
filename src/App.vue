<script>
import NavbarComp from "./components/NavbarComp.vue";
export default{
  components: { NavbarComp },
}
</script>

<template>
  <header>
      <nav>
        <navbar-comp/>
      </nav>
  
  </header>
   
  <RouterView />


</template>

