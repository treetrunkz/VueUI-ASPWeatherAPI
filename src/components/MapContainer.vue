<template>
	<div ref="map-root">
		 style="width: 100%, height 100%">
	</div>
	<div>VIS</div>
</template>

<script>

    import View from 'ol/View'
    import Map from 'ol/Map'
    import TileLayer from 'ol/layer/Tile'
	import OSM from 'ol/source/OSM'
	import 'ol/ol.css'

export default {
	name: 'MapContainer',
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