<template>
  <div>
    <div class="mainBg">
        <div class="backgroundOne"></div>
        <div class="backgroundTwo"></div>
    </div>
    <div style="zIndex: 1;">
        <h1 id="headerName">{{ main.name }}</h1>
        <ul>
            <li>
                <a href=`twitter.com/${{}}`>
                    <i class="fab fa-twitter-square"></i>

                </a>
                <i class="fab fa-twitter">{{ main.social_media.twitter }}</i>
            </li>
            <li>
                
                <a href="">{{ main.social_media.instagram }}</a>
            </li>
            <li><i class="fab fa-twitter"></i></li>
            <li>
                <a href="">{{ main.social_media.snapchat }}</a>
            </li>
            <li>
                <a href="">{{ main.social_media.email }}</a>
            </li>
        </ul>
    </div>
  </div>

</template>

<script>
    import axios from "axios";

    export default {
        name: "Main",
        data() {
            return {
                main: null,
            };
        },
        created: function () {
            axios.get("https://hirng-x2021.glitch.me/api").then((res) => {
                this.main = res.data;
            });
        },
    };
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Dosis:wght@300&display=swap');

    .mainBg {
        position:fixed; 
        height: 100%; 
        z-Index: -1;
    }

    .backgroundOne {
        background-color: #BD0F4D;
        height: 100%;
        width: 50%; 
        position: fixed;
        left: 0;
    }

    .backgroundTwo {
        background-color: #CB2964;
        height: 100%;
        width: 50%; 
        position: fixed;
        right: 0;
    }


    #headerName {
        font-family: 'Dosis';
        margin-top: 20px;
        color: white;
        letter-spacing: 10px;
    }
</style>