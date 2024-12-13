<template>
    <div>
      <h2>{{ wonders.name }}</h2>
      <img :src="wonders.imageUrl" :alt="wonders.name" width="300" height="200" />
      <p><strong>Description:</strong> {{ wonders.description }}</p>
      <p><strong>Location:</strong> {{ wonders.location }}</p>
      <p><strong>Established:</strong>{{wonders.establishedYear }}</p>
      <p><strong>More Info:</strong> {{ wonders.additionalDetail }}</p>
    </div>
</template>

<script>
export default{
    name: 'SingleWonder',
    props:{
        wonders:Array
    },
}
</script>
