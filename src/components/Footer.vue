<template>
    <footer>
        <a class="socialLink" v-for="(socialLink, index) in socialLinks"
           v-bind:key="index" v-bind:href="socialLink.link" target="blank">
            <img v-bind:src="socialLink.icon" v-bind:alt="socialLink.label" v-bind:title="socialLink.label">
        </a>

    </footer>
</template>

<script>

    import api from '../services/api.js';

    export default{
        name:'Footer',
        data(){
            return{
                socialLinks:[]
            }
        },
        mounted(){
            api.get('/social-links.json').then(response => {
               this.socialLinks = response.data
            });
        }
    }
</script>

<style scoped>
    footer{
        width: 100%;
        height: 60px;
        background-color: var(--color-background-nav);
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .socialLink{
        border: 2px solid var(--color-text-light);
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        width: 40px;
        height: 40px;
        margin: 0 10px;
    }

    .socialLink img{
        width: 20px;
    }


</style>