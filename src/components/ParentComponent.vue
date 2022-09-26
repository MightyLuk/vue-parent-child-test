<template>
    <div>
        <h1>Parent</h1>
        <input v-model="parentText">
        <p>{{parentText}}</p>
        <p>{{childText}}</p>
        <ChildComponent :parent-text="parentText" @get-child-text="getChildText"></ChildComponent>
        
    </div>
</template>
<script>
import ChildComponent from './ChildComponent.vue';


export default {
    name: "ParentComponent",
    data() {
        return {
            parentText: "Parent",
            childText: "",
        };
    },
    components: { ChildComponent },
    methods: {
    getChildText(value) {
      console.log(value); // Raja Tamil
      this.childText = value;
   }
 }
}
</script>
<style lang="de">
    
</style>