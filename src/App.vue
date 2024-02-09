<script >
export default{
  name:'App',
  data(){
    return{
      message: 'Hello world',
      image:'https://picsum.photos/200/300',
    }
  },
}
</script>

<template>
 <h1>{{ message }}</h1>
 <img :src="image" alt="random picture">
</template>

<style >

</style>
