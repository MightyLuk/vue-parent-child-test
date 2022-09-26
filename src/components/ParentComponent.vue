<template>
    <div>
        <h1>Parent</h1>
        <input v-model="parentText" />
        <p>{{parentText}}</p>
        <p>{{childText}}</p>
        <li v-for="child in childs" :key="child.id">
            ID: {{child.id}} Text: {{child.childText}}
        </li>
        <ChildComponent :parent-text="parentText" @get-child-text="getChildText"></ChildComponent>
        <ChildComponent :parent-text="parentText" @get-child-text="getChildText"></ChildComponent>
        <ChildComponent v-for="child in childs" :key="child.childText" :initChildText="child.childText"
            :childId="child.id" :parent-text="parentText" @get-child-text="getChildText">

        </ChildComponent>
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
            childKey: 0,
            childs: [
                { id: 1, childText: "Child 1" },
                { id: 2, childText: "Child 2" },
                { id: 3, childText: "Child 3" }
            ]
        };
    },
    components: { ChildComponent },
    methods: {
        getChildText(child) {
            this.childText = child.childText;
            console.log(this.parentText)
            for (let i = 0; i < this.childs.length; i++) {
                console.log(child.childId);
                console.log(this.childs[i]);
                if (child.childId == this.childs[i].id) {
                    this.childs[i].childText = "clicked";
                }
            }
        }
    }

}
</script>
<style lang="de">
    
</style>