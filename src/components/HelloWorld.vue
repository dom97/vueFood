<template>
  <div>
    <div class="food">
      <div v-for="item in items">
        <h2>{{item.title}}</h2>
        <p>{{item.description}}</p>
        <p>{{item.rating}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  data() {
    return {
      items: [
      {        
          description: "test description",
          title: "test title",
          rating: "test rating / 10"
      }
      ]
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
