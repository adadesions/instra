<template >
    <div id="tasklist">
        <div class="ui card" v-for="(name, idx) in names" :key="idx">
            <div  class="image">
                <img :src="info.data.message[idx]">
            </div>
            <div class="content">
                <a class="header">{{ name }}</a>
                <div class="meta">
                <span class="date">Joined in 2013</span>
                </div>
                <div class="description">
                Kristy is an art director living in New York.
                </div>
            </div>
            <div class="extra content">
                <a>
                <i class="user icon"></i>
                22 Friends
                </a>
            </div>
        </div>
        <iframe width="100%" height="350" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://www.openstreetmap.org/export/embed.html?bbox=102.11222290992738%2C14.977036044706901%2C102.11576342582704%2C14.979430201244147&amp;layer=mapnik&amp;marker=14.97823312632122%2C102.1139931678772" style="border: 1px solid black"></iframe><br/><small><a href="https://www.openstreetmap.org/?mlat=14.97823&amp;mlon=102.11399#map=19/14.97823/102.11399">View Larger Map</a></small>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'TaskList',
    data: function() {
        return {
            names: ['Ada', 'Peter', 'Jason', 'Davin Ci', 'Yoda', 'Anakin'],
            info: null
        }
    },
    mounted () {
        axios
        .get('https://dog.ceo/api/breed/pomeranian/images/random/10')
        .then(response => (this.info = response))
    }
}
</script>

<style>
    #tasklist {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
        
    }

    .ui.card:first-child {
        margin-top: 1em;
    }
</style>