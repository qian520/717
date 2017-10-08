<template>
    <div class="mask" :class="{'active':isActive}">
        <img src="../assets/loading.gif" alt="">
       
    </div>
</template>
<script>
export default {
    name: 'mask-view',
    props: ['isActive'],
    mounted() {
        //this.isActive = this.$store.state.mask_active
    },
    methods: {

    }
}
</script>
<style>
.mask {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.7);
    color: #fff;
    display: none;
    justify-content: center;
    align-items: center;
}

.active {
    display: flex;
}


</style>
