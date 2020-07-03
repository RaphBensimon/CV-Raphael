<template>
	<div id="app">
		<header>
			<h1>Raphael BENSIMON</h1>
			<h2>Developpeur web</h2>
		</header>
		<div id="bar_container">
			<img src="@/assets/img/bar.svg">
		</div>
		<router-view/>
		<footer></footer>
	</div>
</template>
<script type="text/javascript"></script>

<style lang="less">
@import '@/assets/css/common.less';
#app {
	position: relative;
	left: 50%;
	transform: translateX(-50%);
	background: @white;
	color: @blue;
	max-width: 818px;
	width: 100%;
	font-size: 14px;
	max-height: 1398px;
}
header {
	display: flex;
	flex-direction: column;
	align-items: center;
	color: @blue;
	text-transform: uppercase;
	margin: 50px 0;
}
header h1 {
	margin: 0;
	font-size: 60px;
	letter-spacing: 3px;
	font-weight: 700;
}
header h2 {
	margin: 0;
	font-size: 25px;
	letter-spacing: 5px;
	font-weight: 400;
}
#bar_container {
	width: 100%;
	height: 37px;
}
#bar_container img {
	object-fit: cover;
	height: 100%;
	width: 100%;
}
footer {
	height: 12px;
	background-color: @red;
}

@media screen and (max-width: 650px) {
	header {
		margin: 15px 0;
	} 
	header h1 {
		font-size: 30px;
	}
	header h2 {
		font-size: 16px;
	}
}

@media screen and (max-width: 350px){
	header h1 {
		font-size: 25px;
	}
	header h2 {
		font-size: 14px;
	}
}
</style>
