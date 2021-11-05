<template>
  <div class="container">
    <div class="card mx-auto" style="width: 18rem">
      <img src="https://picsum.photos/1920/1080?random" class="card-img-top" />
      <div class="card-body">
        <div v-if="results == null">
          <img class="load" src="/img/load.svg" alt="load" />
        </div>
        <div id="cons" v-for="res in results" :key="res.id">
          {{ res.advice }}
        </div>
        <button class="btn">
          <a href="http://192.168.0.13:8080/"
            >Ver outro
            <img class="arrow-right" src="/img/arrow-right.svg" alt="load"
          /></a>
        </button>
      </div>
    </div>
  </div>
</template>

  <script>
export default {
  name: "Advices",
  data() {
    return {
      results: null,
    };
  },

  methods: {
    async getCons() {
      const req = await fetch("https://api.adviceslip.com/advice");
      const data = await req.json();
      this.results = data;
      // console.log(this.results);
    },
  },

  mounted() {
    this.getCons();
  },
};
</script>

<style scoped>
.card {
  border: rgb(113, 89, 193, 0.2);
  border-radius: 1rem;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.card img {
  border: transparent;
  border-radius: 1rem 1rem 0rem 0rem;
}
#cons {
  padding: 2rem;
  background: rgb(113, 89, 193, 0.2);
  border-left: 4px solid #7159c1;
  border-radius: 1rem;
  font-size: 1.2rem;
  font-weight: 600;
  color: #34495e;
}

.btn {
  margin-top: 1rem;
  background: #ffff;
  border-radius: 1.2rem;
  border: 2px solid rgb(113, 89, 193, 0.4);
  font-weight: 600;

  transition: 600ms;
}
.btn:hover {
  border: 2px solid #7159c1;
}

.btn a {
  color: #7159c1;
  text-decoration: none;
}

.load {
  max-width: 4rem;
}
.arrow-right {
  max-width: 1.6rem;
}
</style>