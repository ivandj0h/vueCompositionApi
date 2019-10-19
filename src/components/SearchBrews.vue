<template>
    <div class="brews">
        <h3>Brew Search...</h3>
        <section>
            <form>
                <input type="text" />
                <button>Submit!</button>
            </form>
        </section>
        <div class="search-result">
            <ul>
                <li>
                    <span class="title">Name : </span>
                    <span class="brew"></span>
                </li>
                <li>
                    <span class="title">Street : </span>
                    <span class="brew"></span>
                </li>
                <li>
                    <span class="title">City : </span>
                    <span class="brew"></span>
                </li>
                <li>
                    <span class="title">Zip : </span>
                    <span class="brew"></span>
                </li>                                                
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