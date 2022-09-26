<template>
    <div>
        <h1>Child</h1>
        <input v-model="childText">
        <p>{{childText}}</p>
        <button @click="this.$emit('getChildText', this)">click me</button>
        <p>{{parentText}}</p>

    </div>
</template>
<script>
export default {
    name: 'ChildComponent',
    props: {
        parentText: String,
        initChildText: String,
        childId: Number
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