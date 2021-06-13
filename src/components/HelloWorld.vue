<!-- @format -->

<template>
	<v-container>
		<div class="  absolute">
			<div v-for="(item, i) in modulesAdmin" :key="i">
				<v-tooltip top>
					<template v-slot:activator="{ on, attrs }">
						<v-btn
							v-bind="attrs"
							v-on="on"
							:class="item.class"
							class="mx-2"
							fab
							large
							:elevation="elevation"
							width="70px"
							height="70px"
						>
							<!-- {{ item.title }} -->
							<v-img width="30px" height="30px" :src="item.urlImg" contain />
						</v-btn>
					</template>
					<span>{{ item.msj }}</span>
				</v-tooltip>
			</div>
		</div>
		<div id="mapa">
			<v-img height="100vh" cover :src="require('@/assets/img/mapa.png')" />
		</div>
		<v-tooltip left>
			<template v-slot:activator="{ on, attrs }">
				<v-btn class="btn-end__session" v-bind="attrs" v-on="on">
					<v-img width="10px" :src="require('@/assets/img/off.svg')" contain />
				</v-btn>
			</template>
			<span>Cerrar Sesión</span>
		</v-tooltip>
	</v-container>
</template>

<script>
	export default {
		name: 'HelloWorld',

		data: () => ({
			show: false,
			elevation: 6,
		}),
		computed: {
			modulesAdmin() {
				const modulesAdmin = [
					{
						urlImg: require('@/assets/img/delivered.svg'),

						class: 'btn_servicios',
						msj: 'SERVICIOS',
					},
					{
						urlImg: require('@/assets/img/report.svg'),

						class: 'btn_personal',
						msj: 'REPORTE',
					},
					{
						urlImg: require('@/assets/img/routes.svg'),

						class: 'btn_ruta',
						msj: 'RUTA',
					},
					{
						urlImg: require('@/assets/img/incidence.svg'),
						class: 'btn_flota',
						msj: 'INCIDENCIA',
					},
					{
						urlImg: require('@/assets/img/bus.svg'),

						class: 'btn_reporte',
						msj: 'FLOTA',
					},
					{
						urlImg: require('@/assets/img/personal.svg'),
						title: 'Incidencia',

						class: 'btn_incidencia',
						msj: 'PERSONAL',
					},
					{
						urlImg: require('@/assets/img/config.svg'),
						title: 'Configuración',

						class: 'btn_config',
						msj: 'CONFIGURACIÓN',
					},
				];
				return modulesAdmin;
			},
		},
	};
</script>
<style lang="scss" scoped>

.container{
  width: auto!important;
}
	.btn_servicios,
	.btn_personal,
	.btn_ruta,
	.btn_flota,
	.btn_reporte,
	.btn_incidencia,
	.btn_config {
		position: relative !important;
	}
	.btn_servicios {
		top: 220px;
		background: rgb(246, 168, 90) !important;
	}
	.btn_personal {
		top: 210px;
		right: 100px;
		background: rgb(163, 190, 235) !important;
	}
	.btn_ruta {
		top: 140px;
		left: 100px;
		background: rgba(105, 207, 92, 0.664) !important;
	}
	.btn_flota {
		top: 180px;
		right: 100px;
		background: rgba(233, 65, 65, 0.781) !important;
	}
	.btn_reporte {
		top: 180px;
		background: rgb(88, 189, 158) !important;
	}
	.btn_incidencia {
		top: 40px;
		left: 100px;
		background: rgb(199, 136, 84) !important;
	}
	.btn_config {
		top: -80px;
	}
	#mapa {
		height: 100vh;
		width: 100vw;
		position: absolute;
		top: 0;
    left:0;
		.v-image {
			filter: blur(4px);
		}
	}
	.absolute {
		position: relative;
		z-index: 2;
	}

	.btn-end__session {
		border: none !important;
		width: 50px !important;
		height: 60px !important;
		bottom: 33px;
		right: 22px;
		position: absolute;
		border-radius: 100%;
	}
	@media screen and (max-width: 400px) {
		.absolute {
			
			top:-70px;
		}
	}
</style>
