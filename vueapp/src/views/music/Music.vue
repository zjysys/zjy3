<template>
    <div>
        <img v-for="(obj,index) in music" :key="index" :src="obj.bg"/>
    </div>
</template>

<script>
    import Axios from 'axios';
    export default {
        data(){
            return {
                music:[]
            }
        },
        created(){
            Axios.get("/data/musiclist.json")
            .then((result)=>{
                this.music = result.date.albums;
            })
        }
        
    }
</script>

<style scoped>

</style>