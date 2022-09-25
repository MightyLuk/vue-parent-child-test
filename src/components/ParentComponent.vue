<template>
    <div>
        <h1>Parent</h1>
        <ChildComponent></ChildComponent>
        
    </div>
</template>
<script>
import ChildComponent from './ChildComponent.vue';


export default {
    name: "ParentComponent",
    data() {
        return {
            ParentText: "Parent",
            ChildText: "",
        };
    },
    components: { ChildComponent }
}
</script>
<style lang="de">
    
</style>