<template>
  <router-link v-bind:to=to class="music">
    <div id="index">{{ index }}</div>
    <div id="info">
      <img v-bind:src=img alt="">
      <div id="title_artist">
        <div id="title">{{ album.name }}</div>
      </div>
    </div>
    <a id="album" href=""></a>
    <div id="date">{{ album.created }}</div>
    <div id="time">{{ album.quantity }}</div>
  </router-link>
</template>

<script>
export default {
  name: "AlbumItem",
  props: {
    index: Number,
    album: Object
  },
  data() {
    return {
      img: "http://localhost:8080/image/" + this.album.image.name,
      to: "/album" + "?id=" + this.album.id
    }
  }
}
</script>

<style scoped>

.music {
  display: flex;
  flex-direction: row;
  font-size: 16px;
  height: 56px;
  color: #a0a0a0;
  align-items: center;
  font-family: 'Roboto', sans-serif;
  border-radius: 4px;
  line-height: normal;
}

#info img {
  width: 40px;
  height: 40px;
  object-fit: cover;
  object-position: 0 0;
}

#index {
  width: 3%;
  display: flex;
  justify-content: center;
}

#info {
  display: flex;
  width: 40%;
}

#title_artist {
  padding: 0 0 0 16px;
  display: flex;
  align-items: center;
}

#title {
  color: #1d1d1d;
}

#album {
  display: flex;
  color: #a0a0a0;
  width: 30%;
}

#album:hover {
  transition: 0.3s;
  text-decoration: underline;
}

#date {
  display: flex;
  width: 20%;
}

#time {
  width: 7%;
  display: flex;
  justify-content: center;
}

.music:hover {
  transition: 0.3s;
  background-color: #dbdbdb;
}

.music:not(:hover) {
  transition: 0.3s;
}

</style>