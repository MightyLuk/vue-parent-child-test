<template>
    <div>
        <h1>Child {{childId}}</h1>
        <input v-model="childText">
        <p>{{childText}}</p>
        <button @click="this.$emit('getChildText', this)">click me</button>
        <p>{{parentText}}</p>
        <p v-if="clicked">clicked</p>

    </div>
</template>
<script>
export default {
    name: 'ChildComponent',
    props: {
        parentText: String,
        initChildText: String,
        childId: Number,
        clicked: Boolean
    },
    data() {
        return {
            //            ParentText: '',
            childText: this.initChildText
        }
    }

}
</script>
<style lang="">
    
</style>