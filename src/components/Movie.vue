<template>
  <div class="movie">
    <div class="container">
      <div class="poster">
        <img src="{{{movie.Poster}}}" />
      </div>
    </div>
    <div class="container">
      <h4>{{{movie.Title}}} <span class="badge">{{{movie.imdbRating}}}</span></h4>
      <p>{{{movie.Plot}}}</p>

      <span v-for="attr in attrs" class="extra_info">{{{attr}}}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    movie: Object
  },

  computed: {
    attrs() {
      return [this.movie.Released, this.movie.Genre]
    }
  }
}
</script>

<style>
* {
  font-family: "Helvetica Neue";
}

.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: 700;
  line-height: 1;
  color: #FFF;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  background-color: #777;
  border-radius: 10px;
}

.movie {
  margin-bottom: 45px;
}

.container {
  display: table-cell;
  vertical-align: top;
}

.poster {
  float: left;
  width: 150px;
  padding: 20px 10px;
  height: 200px;
}

.poster img {
  max-height: 200px;
}

.extra_info {
  display: block;
  float: left;
  margin-right: 15px;
}
</style>
