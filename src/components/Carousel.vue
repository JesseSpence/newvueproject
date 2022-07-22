<template>
  <div class="Carousel">
<slot></slot>

<button @click="nex" class="nex">Next</button>

<button @click="prev" class="prev">Prev</button>
  </div>
</template>

<script>

export default {
    data() {

    },
    methods: {
        nex() {
        this.$emit('nex')
        },
     prev() {
        this.$emit('prev')
    }
}
}

</script>

<style scoped>
.Carousel{
    position: relative;
    width: 600px;
    height:350px;
    overflow:hidden;
}
button {
    position:absolute;
    height: 40px;
    width: 50px;
    top: calc(50% - 0px);
    background-color:rgba(0, 0, 0, 0.822);
    color:white;
    border:none;
}
button:focus, button:hover {
    outline:none;
    cursor:pointer;
}
.nex {
    right:0
}
.prev {
    left:0
}
</style>