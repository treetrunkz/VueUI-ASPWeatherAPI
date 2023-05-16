<template>
    <div id="app">
        <div ref="map-root" class="cell cell-map">
        </div>
        <div class="cell cell-edit">
            Edit
        </div>
        <div class="cell cell-inspect">
            Inspect
        </div>
    </div>
    <MapContainer />
</template>

<script>
  import View from 'ol/View'
  import Map from 'ol/Map'
  import TileLayer from 'ol/layer/Tile'
  import OSM from 'ol/source/OSM'

  // importing the OpenLayers stylesheet is required for having
  // good looking buttons!
  import 'ol/ol.css'
    export default {
        name: 'App',
	    components: {},
	    props: {},
	    mounted() {
		    new Map({
		    target: this.$refs['map-root'],
		    layers: [
			    new TileLayer({
				    source: new OSM()
			    }),
		    ],

		    view: new View({
		    zoom:0,
		    center: [0,0],
		    constrainResolution: true
		    }),
	    })
	    },
    }
</script>

<style>
    html, body {
        height: 100%;
        margin: 0;
    }

    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        height: 100%;
        display: grid;
        grid-template-columns: 100vh;
        grid-auto-rows: 1fr;
        grid-gap: 1rem;
        padding: 1rem;
        box-sizing: border-box;
    }

    .cell {
        border-radius: 4px;
        background-color: lightgrey;
    }

    .cell-map {
        grid-column: 1;
        grid-row-start: 1;
        grid-row-end: 3;
    }

    .cell-edit {
        grid-column: 2;
        grid-row: 1;
    }

    .cell-inspect {
        grid-column: 2;
        grid-row: 2;
    }
</style>











<!--<template>
    <div class="post">
        <div v-if="loading" class="loading">
            Loading... Please refresh once the ASP.NET backend has started. See <a href="https://aka.ms/jspsintegrationvue">https://aka.ms/jspsintegrationvue</a> for more details.
        </div>

        <div v-if="post" class="content">
            <table>
                <thead>
                    <tr>
                        <th>Date</th>
                        <th>Temp. (C)</th>
                        <th>Temp. (F)</th>
                        <th>Summary</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="forecast in post" :key="forecast.date">
                        <td>{{ forecast.date }}</td>
                        <td>{{ forecast.temperatureC }}</td>
                        <td>{{ forecast.temperatureF }}</td>
                        <td>{{ forecast.summary }}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script lang="js">
    import { defineComponent } from 'vue';

    export default defineComponent({
        data() {
            return {
                loading: false,
                post: null
            };
        },
        created() {
            // fetch the data when the view is created and the data is
            // already being observed
            this.fetchData();
        },
        watch: {
            // call again the method if the route changes
            '$route': 'fetchData'
        },
        methods: {
            fetchData() {
                this.post = null;
                this.loading = true;

                fetch('weatherforecast')
                    .then(r => r.json())
                    .then(json => {
                        this.post = json;
                        this.loading = false;
                        return;
                    });
            }
        },
    });
</script>-->
