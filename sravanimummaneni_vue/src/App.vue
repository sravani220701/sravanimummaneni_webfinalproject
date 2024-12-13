<template>
  <div id="app">
    <div class="main-image-container">
      <img 
        alt="wonders-of-the-world" 
        src="https://i.postimg.cc/GtwtyfBq/desktop-wallpaper-seven-wonders-7-wonders-of-the-world.jpg" 
        class="main-image"
      />
    </div>
    <div class="wonder-card-container">
      <WonderCard :wonders="wonders" />
      <MyHeader
        name="Great Wall of China"
        description="An ancient series of walls and fortifications located in northern China."
        location="China"
        establishedYear="700 BCE"
        additionalDetail="One of the most famous architectural achievements in history."
        imageUrl="https://upload.wikimedia.org/wikipedia/commons/thumb/2/23/The_Great_Wall_of_China_at_Jinshanling-edit.jpg/640px-The_Great_Wall_of_China_at_Jinshanling-edit.jpg"
      />
    </div>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'; 
import WonderCard from './components/WonderCard.vue';

export default {
  name: 'App',
  components: {
    WonderCard,
    MyHeader
  },
  data() {
    return {
      wonders: []
    };
  },
  methods: {
    async fetchwonders() {
      try {
        const res = await fetch('https://wonderback-2.onrender.com/api');
        const data = await res.json();
        console.log(data);
        return data;
      } catch (error) {
        console.error("Error fetching wonders:", error);
      }
    }
  },
  async created() {
    this.wonders = await this.fetchwonders();
  }
};
</script>

<style>
#app {
  font-family:'Times New Roman';
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
  text-align:left;
  color: #181819;
  margin-top:0px;
  display:flex;
  flex-direction:column;
  align-items:center;
  background-image:linear-gradient(15deg,#FFDEE9 0%,#caf9f8 100%);
}

.main-image-container {
  margin:20px 0;
  width:97%; 
}

.main-image {
  width:100%;
  height:680px;
  border-radius:8px;
}

.wonder-card-container {
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
  gap:20px;
  padding:0px;
}

.wonder-card h1,
.wonder-card h2,
.wonder-card h3 {
  text-align:center; 
  color:#0c0c0c;
  margin:8px 0;
}
</style>
