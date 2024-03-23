<script>
    export default {
        data() {
            return {
                newNameInput: "",
                suffixInput: "[OFFICIAL MUSIC VIDEO]",
            }
        },
        methods: {
            nameAdded(){
                this.$emit('name-added', this.newNameInput)
            },
            suffixAdded(){
                this.$emit('suffix-added', this.suffixInput)
            }
        },
        mounted(){
            this.$emit('suffix-added', this.suffixInput)
        }
    }
</script>

<template>
  <div class="w-full md:w-2/6 flex flex-col gap-5">
    <div>
        <label for="name">Novi naziv</label>
        <input id="name" type="text" class="border rounded w-full p-1" v-model="newNameInput" @keyup="nameAdded"/>
    </div>
    <div>
        <label for="suffix">Sufiks</label>
        <input id="suffix" type="text" class="border rounded w-full p-1" v-model="suffixInput" @keyup="suffixAdded"/>
    </div>
    <!-- <ul class="border rounded w-full">
        <li v-for="item in list" :key="item.id" :class="{active: item.value === selected}" @click="$emit('selection-change', item.value)">
            <div class="flex justify-between">
                <p>{{item.value}}</p>
                <div class="flex gap-2">
                    <span><i class="fa-solid fa-pen-to-square"></i></span>
                    <span><i class="fa-solid fa-trash text-red-300"></i></span>
                </div>
            </div>
        </li>
    </ul> -->
  </div>
</template>

<style scoped>
    .active {
        background-color: #474455;
    }

    ul li {
        padding: 4px 10px;
        cursor: pointer;
    }

    ul li:hover {
        background-color: #2d2b36;
    }
</style>
