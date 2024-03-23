<script>  
    export default {
        props: ["name", "suffix", "textTransform"],
        data(){
            return {
                songList: ["Neka vozi", "Ona živi za noć", "Mašta radi svašta", "Daleko", "Mrak"], 
            }
        },
        methods: {
          async copy(){
            const text = this.songList.map(x => `${this.name} - ${x} ${this.suffix}`).join("\n")
            await navigator.clipboard.writeText(text)
            this.$toast.default("Kopirano", { position: "bottom", duration: 1000 })
          }
        }
    }
</script>

<template>
  <div @click="copy()" class="cursor-pointer border rounded flex-grow mt-5 p-3 font-bold text-sm md:text-lg" v-if="name !== ''">
    <h2 class="py-1" v-for="song in songList" :key="song">{{name}} - <span :style="{ textTransform: textTransform }">{{song}}</span> {{suffix}}</h2>
  </div>
</template>

<style scoped>

</style>
