<template>
    <div class="wonder-card">
      <h2>{{ name }}</h2>
      <img :src="imageUrl" :alt="name" width="300" height="200" />
      <p><strong>Description:</strong> {{ description }}</p>
      <p><strong>Location:</strong> {{ location }}</p>
      <p><strong>Established:</strong> {{establishedYear}}</p>
      <p><strong>More Info:</strong> {{ additionalDetail }}</p>
    </div>
</template>

<script>
export default{ 
    name: 'MyHeader',
    props:{ 
        name:String,
        imageUrl:String,
        description: String,
        location:String,
        establishedYear:String,
        additionalDetail:String,
    }
}
</script>

<style scoped>
div{
    text-align: center;
}
</style>