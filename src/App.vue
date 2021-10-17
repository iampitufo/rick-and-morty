<template>
<div class="container">
  <h1> Rick and Morty </h1>  

  <FilterByStatus />
  <FilterByName />
  <ListCharacters /> 
  </div>
</template>

<script>
import ListCharacters from '@/components/ListCharacters'
import FilterByStatus from '@/components/FilterByStatus'
import FilterByName from '@/components/FilterByName'

export default {
  name: 'App',
  components: {
    ListCharacters,
    FilterByName,
    FilterByStatus
  }
}
</script>

<style lang="scss">
:root{
  --background-body: #24282F;
  --background-card: #3C3E44;
  --text-white: #ffffff;
  --text-gray: #C0C0C0;
  --text-orange: #FF9800;
}

*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  background-color: var(--background-body);
  color: var(--text-white);
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.container{
  width: 980px;
  max-width: 90%;
  margin: 5rem auto;
}

h1 {
  margin-bottom: 3rem;
  text-align: center;
}

img{
  width: 100%;
}
</style>
