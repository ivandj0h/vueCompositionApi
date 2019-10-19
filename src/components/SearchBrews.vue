<template>
    <div class="brews">
        <h3>Brew Search...</h3>
        <section>
            <form>
                <input type="text" class="form-control" />
                <button class="btn btn-secondary">Submit!</button>
            </form>
        </section>
    <div v-if="error">
      <h2>erorr!! {{ error }}</h2>
    </div>
    <div v-if="fetching"><h2>Fetching Data!</h2></div>
    <div class="search-results" v-for="brewery in list" :key="brewery.id">
      <ul>
        <li><span class="title">Name:</span> <span class="brew">{{ brewery.name }}</span></li>
        <li><span class="title">Street:</span> <span class="brew">{{ brewery.street}}</span></li>
        <li><span class="title">City:</span><span class="brew"> {{ brewery.city }}</span></li>
        <li><span class="title">Zip:</span><span class="brew"> {{brewery.postal_code}}</span></li>
      </ul>
    </div>
  </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
    .search-result {
        display: flex;
        width: 600px;
        text-align: left;
    }
    .brews {
        max-width: 1024px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        margin: 0 auto;
    }
    ul {
        list-style: none;
        width: 100%;
    }
    li {
        display: flex;
        justify-content: space-between;
    }
    .brew {
        font-weight: bold;
    }
</style>