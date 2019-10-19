<template>
  <div class="container">
    <div class="ro">
      <div class="md-3">
        <div class="form-group">
          <h3>Pencarian</h3>
          <form @submit.prevent="submitted">
            <div class="form-group">
              <div class="input-group mb-3">
                <div class="custom-file">
                  <input
                    v-model="val"
                    type="text"
                    class="form-control"
                    placeholder="Masukan Kata..."
                  />
                </div>
                <div class="input-group-append">
                  <button class="input-group-text">Submit</button>
                </div>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>

    <div v-if="error">
      <h2>erorr!! {{ error }}</h2>
    </div>
    <div v-if="fetching">
      <small class="form-text text-muted">Fetching Data!</small>
    </div>
    <div class="search-results" v-for="brewery in list" :key="brewery.id">
      <div class="card border-secondary mb-3" style="max-width: 50rem;">
        <div class="card-header">{{ brewery.email }}</div>
        <div class="card-body">
          <h4 class="card-text1">{{ brewery.name }}</h4>
          <p class="card-text">{{ brewery.body}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import useBrewList from "../composition/use-brew-list";

import { createComponent } from "@vue/composition-api";
export default createComponent({
  setup() {
    const { submitted, list, val, error, fetching } = useBrewList();
    return {
      val,
      list,
      submitted,
      error,
      fetching
    };
  }
  //   data() {
  //     return {
  //       val: "",
  //       breweries: []
  //     };
  //   },
  //   methods: {
  //     async submitted(event) {
  //       console.log();
  //       const response = await fetch(
  //         `https://api.openbrewerydb.org/breweries/?by_name=${this.val}`
  //       ).then(res => res.json());
  //       console.log(response);
  //       this.breweries = response;
  //       event.preventDefault();
  //     }
  //   }
});
</script>

<style scoped>
.search-results {
   display: inline-block;
    height: 75px;
    margin: 10px;
    text-align: left;

}
.search-results card {
    border: 1px solid #ddd; 
}

.card-text {
  font-size: 2vh;
}
</style>
