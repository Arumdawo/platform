<template>
	<button class="button" :class="{'small': isSmall}">
		<LoadingDots v-if="loading" />
		<i v-if="((iconClassName) && (!loading))" :class="iconClassName"></i>
		<span v-if="!loading">{{buttonTxt}}</span>
	</button>	
</template>

<script>
import LoadingDots from './LoadingDots.vue';
/**
 * @description
 * Button Widget
 */
export default {
	name: 'ButtonWidget',
	props: {
		/**
		 * Button Text
		 */
		buttonTxt: {
			type: String,
			default: '',
		},
		/**
		 * Icon Class name's
		 */
		iconClassName: {
			type: String,
			default: '',
		},
		/**
		 * change to small button display
		 */
		isSmall: {
			type: Boolean,
			default: false,
		},
		/**
		 * animated loading display
		 */
		loading: {
			type: Boolean,
			default: false,
		},
	},
	components: {
		LoadingDots,
	},
};
</script>

<style scoped>

button * {
	cursor: pointer;
}
.button {
	border:0px;
	border-radius:6px;
	color:#fff;
	text-align:center;
	height: 40px;
	line-height: 40px;
    display: flex;
    width: 280px;
    margin: 0px auto;
	text-transform: uppercase;
	letter-spacing: 0.2px;
	cursor: pointer;
	transition:background 0.2s;
	padding:0px 16px;
	font-family: 'Nunito', sans-serif;
	justify-content: center;
}
.disable {
	opacity:0.1;
	cursor: default;
}

button.disable * {
	cursor: default;
}

.night button {
	background-color:#101219;
	color:#afafaf;
}
.light button {
	background-color:#3598db;
}
.night button:hover {
	background-color:#000;
	color:#fff;
}
.light button:hover {
	background-color:#1970c7;
}

button.small {
	height: 30px;
	line-height:30px;
	font-size:0.7em;
	width:auto;
	margin:0px 2px;
}

.night button.green {
	background-color:#1bb394;
	color:#101219;
	font-weight:bold;
}
.light button.green {
	background-color:#1bb394;
	color:#fff;
	font-weight:bold;
}
.night button.green:hover {
	background-color:#14a381;
	color:#fff;
}


button.red {
    background-color: #fe6963;
    color: #fff;
    font-weight: bold;
    display: flex;
    justify-content: center;
}
button.red:hover {
	color:#fff;
    background-color: #fe504b;
}
.night button.red {
	color:#fff;
}
.night button.red:hover {
	color:#fff;
}

.night .green .miningIco,
.night .miningIco {
	background-color: #000; 
}

.night .red .miningIco,
.night .green:hover .miningIco,
.night .red:hover  .miningIco,
.light .miningIco {
	background-color: #fff; 
}

.miningIco {
	width: 48px;
	height: 40px;
    margin-left: -40px;
	display: inline-block;

	-webkit-mask: url('../../assets/pickaxe.svg') no-repeat 50% 50%;
	mask: url('../../assets/pickaxe.svg') no-repeat 50% 50%;
	-webkit-mask-size: cover;
	mask-size: cover;
}
</style>