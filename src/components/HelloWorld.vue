<template>
  <div>
    <div class="food">
      <button @click="toggleSort('title')">SortTitle</button>
      <button @click="toggleSort('rating')">SortRating</button>
      <button @click="toggleSort('description')">SortDescription</button>
      <button @click="reverseSort">ReverseSort</button>
      <div v-for="item in sortedItems">
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
      },
      {        
          description: "a",
          title: "s",
          rating: "d"
      },
      {        
          description: "d",
          title: "s",
          rating: "a"
      },
      {        
          description: "s",
          title: "d",
          rating: "a"
      }
      ],
      sort: 'title',
      reverse: false
    }
  },
  computed: {
    sortedItems: function() {
        if (this.reverse) {
          return this.items.sort((a,b) => (a[this.sort] > b[this.sort]) ? 1 : ((b[this.sort] > a[this.sort]) ? -1 : 0)) 
        } else {
          return this.items.sort((a,b) => (a[this.sort] > b[this.sort]) ? -1 : ((b[this.sort] > a[this.sort]) ? 1 : 0)) 
        }
    }
  },
  methods: {
    toggleSort: function(type) {
      this.sort = type;
    },
    reverseSort: function() {
      this.reverse = !this.reverse;
    }
  }
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
