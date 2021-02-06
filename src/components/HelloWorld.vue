<template>
  <div class="hello">
    <h1 v-format="'upperCase'" v-show="enable">{{ msg }}</h1>
    <span v-html="names"></span>
    <hr />
    <ul>
      <li v-for="(item, index) in movies" :key="index">
        {{ index + 1 }} - {{ item.name }} - {{ item.year }}
      </li>
    </ul>

    <label v-format="'minuscula'">MENSAJE EN MINUSCULA</label>
    <label v-format="'mayuscula'">mensaje en mayuscula</label>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      enable: true,
      names: `<h2>
                <i>Roberto Antonio Quintanilla Aguilar
                <br />
                Gabriela Alexandra Gallardo Alvarez</i>
              </h2>`,
      movies: [
        { name: "The Godfather", year: 1972 },
        { name: "Back to the Future", year: 1985 },
        { name: "Rocky", year: 1976 },
        { name: "Taxi Driver", year: 1976 },
        { name: "Jurassic Park", year: 1993 },
        { name: "Forrest Gump", year: 1994 },
        { name: "Titanic", year: 1997 },
        { name: "The Matrix", year: 1999 },
        { name: "Gladiador", year: 2000 },
        { name: "The Avengers", year: 2012 },
      ],
    };
  },
  directives: {
    format: function(el, binding) {
      if (binding.value == 'mayuscula') {
        el.style.textTransform = 'upperCase'
      } else if (binding.value == 'minuscula') {
        el.style.textTransform = 'lowerCase'
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 15px;
}
li {
  margin: 0 10px;
  font-size: 18px;
  padding: 5px;
}

label {
  margin: 10px 0 0;
  display: block;
}



a {
  color: #42b983;
}
</style>
