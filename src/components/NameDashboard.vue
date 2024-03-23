<script>
import NameExamples from './NameExamples.vue'
import NameList from './NameList.vue'

    export default {
        components: { NameList, NameExamples },
        data(){
            return {
                name: "",
                suffix: "",
                textTransform: "",
            }
        },
        methods: {
            nameAdded(value){
                this.name = value;
            },
            suffixAdded(value){
                this.suffix = value;
            },
            textTransformChanged(value){
                this.textTransform = value;
            }
        }
    }
</script>

<template>
  <div class="flex flex-col md:flex-row gap-5 px-3 md:px-0">
    <name-list @name-added="nameAdded" @suffix-added="suffixAdded" @text-transform-changed="textTransformChanged" />
    <name-examples :name="name" :suffix="suffix" :textTransform="textTransform" />
  </div>
</template>

<style scoped>

</style>
