<template>
    <div @submit="prevent" class="mx-36 flex flex-row justify-center">
        <input class="font-serif w-9/12 text-black" @keydown.enter="changeNews" type="text" v-model="searchQ" placeholder="Search"/>
            <div class="secsearchbtn">
                <SecSearchButton v-on:click="changeNews"/>
            </div>
    </div>
</template>

<script>
import SecSearchButton from '../components/SecSearchButton.vue'

export default {
    components: {
        SecSearchButton       
    },
    data() {
        return {
            searchQ: ''
        }
    },
    methods: {
        changeNews() {
            this.$emit("newsChanged", this.searchQ);
            this.searchQ = '';
        }
    }
}
</script>

<style scoped>
.secsearchbtn {
    border: 1px dotted #000; 
    border-radius: 5px;
    padding: 0.5rem;
}

input[type=text] {
    border: 1px dotted #000;
    box-sizing: border-box;
    border-radius: 5px;
    background: transparent;
    height: 2rem;
    outline: none;
    color: black;
    padding-top: 1.2rem;
    padding-left: 1.2rem;
    padding-bottom: 1.2rem;
    padding-right: 0.5rem;
    /* width: 95%; */
    font-weight: 400;
}

::placeholder {
    color: #000;    
}

</style>