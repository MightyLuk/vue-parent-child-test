<template>
    <div>
        <h1>Child</h1>
        <input v-model="childText">
        <p>{{childText}}</p>
        <button @click="this.$emit('getChildText', childText)">click me</button>
        <p>{{parentText}}</p>
        
    </div>
</template>
<script>
export default {
    name: 'ChildComponent',
    props: {
        parentText: String,
    },
    data() {
        return {
//            ParentText: '',
            childText: 'Child'
        }
    }
    
}
</script>
<style lang="">
    
</style>