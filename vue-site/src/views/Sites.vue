<template>
    <div class="sites">
        <sites-create :options="createOptions"></sites-create>
        <sites-list :list="list" :fields="tableFields"></sites-list>
    </div>
</template>

<script>
import axios from 'axios';
import SitesCreate from '@/components/SitesCreate';
import SitesList from '@/components/SitesList';
export default {
    data() {
        return {
            list: [],
            tableFields: ['url', 'ip', 'server', 'user', 'dns', 'lb', 'log'],
            createOptions: [
          { text: 'Staging Site', value: 'staging' },
          { text: 'Automatic Updates', value: 'authomatic' },
          { text: 'Update DNS', value: 'dns' }
        ]

        }
    },
    mounted() {
        axios.get('https://api.myjson.com/bins/10pdkk')
            .then((response) => {
                this.list = response.data;
        });
    },
    components: {
        SitesCreate,
        SitesList
    }
}
</script>

<style>
    .sites {
        width: 100%;
        background-color: grey;
        color: black;
        padding: 100px 0;
    }
</style>