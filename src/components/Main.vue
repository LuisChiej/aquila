<template>

<div>

   
   
        <h3> {{main.name}} </h3>
        <ul>
        <li><i class="fab fa-twitter">{{main.social_media.twitter}}</i></li>
        <li><a href="">{{main.social_media.instagram}}</a></li>
        <li> <i class="fab fa-twitter"></i></li>
        <li><a href="">{{main.social_media.snapchat}}</a></li>
        <li><a href="">{{main.social_media.email}}</a></li>

        </ul>
      
</div>
    
   
</template>

<script>
import axios from 'axios';

export default {
    name: 'Main',
    data(){
        return {
            main: null,
        };
    },
    created: function(){
        axios
            .get('https://hirng-x2021.glitch.me/api')
            .then(res => {
                this.main = res.data;
            })
    }
}
</script>

<style scoped>

</style>