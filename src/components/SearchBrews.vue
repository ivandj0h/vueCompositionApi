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
                    <input v-model="val" type="text" class="form-control" placeholder="Masukan Kata..." />
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
<small
            id="emailHelp"
            class="form-text text-muted"
          >Fetching Data!</small>
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

</style>
