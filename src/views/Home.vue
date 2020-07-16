<template>
 	<main id="home">
		<div id="left_content">
			<img id="profile_picture" alt="Raphaël BENSIMON" src="@/assets/img/raphael.jpg">
			<div class="content">
				<h3>Contact</h3>
				<p class="iconed"><img src="@/assets/img/call.svg"><a class="no_decoration" href="tel:+33658759117">06 58 75 91 17</a></p>
				<p class="iconed"><img src="@/assets/img/mail.svg"><a class="no_decoration" href="mailto:rbensimon05@gmail.com">rbensimon05@gmail.com</a></p>
				<p class="iconed"><img src="@/assets/img/location.svg"><a class="no_decoration" target="_blank" href="https://goo.gl/maps/QZzqDkK6vZ6GmYxw5">Villemomble, 93250</a></p>
				<p class="iconed"><img src="@/assets/img/logo-github.svg"><a target="_blank" href="https://github.com/RaphBensimon">https://github.com/RaphBensimon</a></p>
			</div>
			<div class="content">
				<h3>Formations</h3>
				<p><b>BAC STL</b><br><i>Lycée Gregor Mendel</i></p>
				<p><b>Classe prépratoire web</b><br><i>ORT Montreuil 2016</i></p>
				<p><b>Bachelor CSI</b> (Sans TOEIC)<br><i>ORT Montreuil 2017</i></p>
				<p><b>Master MS2I</b> (Non Obtenu)<br><i>ORT Montreuil 2020</i></p>
			</div>
			<div class="content">
				<h3>Passion</h3>
				<p>Automobile</p>
			</div>
		</div>
		<div id="right_content">
			<p id="description">En tant que développeur web, mon objectif est de comprendre les besoins des	clients, des équipes internes et de les convertir en une <b>solution web</b>, en respectant les contraintes de temps sans négliger la qualité. De nature positive,	je suis à l'écoute des <b>dernières technologies</b> web que je mets en place lors de
			projet avec mon équipe.
			</p>
			<div class="content">
				<h3>Expérience</h3>
				<div class="exp">
					<h4>Data4job</h4>
					<p class="info">Développeur web front-end / Alternance / 2017 - 2020</p>
					<p class="description">Développement web (VueJS, Meteor, NodeJS) des différentes plateformes web
					de l'entreprise.</p>
				</div>
				<div class="exp">
					<h4>ImmoJeune</h4>
					<p class="info">Intégrateur / Stage / 6 mois / 2016</p>
					<p class="description">Intégration web natif de landing page à l'aide de maquette graphique (HTML,CSS, JS).</p>
				</div>
			</div>
			<div class="content" id="competences">
				<h3>Compétences</h3>
				<ul>
					<li v-for="comp in competences">
						<p :style="comp.bold ? 'font-weight: 700;': 'font-weight: 400;'">{{comp.name}}</p>
						<div class="pourcent" :style="{width: comp.pourcent * 1.5 + 'px'}"></div>
					</li>					
				</ul>
			</div>
		</div>
 	</main>
</template>

<script>
export default {
	name: 'Home',
	data() {
		return {
			competences: [
				{name: 'HTML', pourcent: 100, bold: false},
				{name: 'CSS/LESS', pourcent: 100, bold: false},
				{name: 'Javascript', pourcent: 80, bold: true},
				{name: 'VueJS/Meteor', pourcent: 80, bold: true},
				{name: 'NodeJS', pourcent: 50, bold: false},
				{name: 'MongoDB', pourcent: 50 , bold: false}			]
		}
	},
}
</script>
<style lang=less>
@import '@/assets/css/common.less';
#home {
	display: flex;
	color: @blue;
}
#home #left_content {
	width: 40%;
	height: 100%;
	background-color: @grey;
	padding: 0 40px;
	padding-bottom: 50px;
	display: flex;
	flex-direction: column;
}
#home #left_content #profile_picture {
	border-radius: 50%;
	align-self: center;
	margin-top: 30px;
}
#home #right_content {
	width: 60%;
	padding: 0 40px;
	padding-bottom: 50px;
	display: flex;
	flex-direction: column;
}
#home #right_content #description {
	line-height: 20px;
	margin-top: 60px;
	margin-bottom: 0px;
	font-size: 14px;
}
#home #right_content #competences {
	margin-top: 20px;
}
#home #right_content #competences ul {
	padding: 0;
	margin: 10px 0 0 0;
}
#home #right_content #competences ul li {
	list-style: none;
	display: flex;
	align-items: center;
}
#home #right_content #competences ul li p {
	margin: 3px 0;
	width: 100px;
}
#home #right_content #competences ul li .pourcent {
	background-color: @red;
	height: 10px;
}
.content {
	margin-top: 30px;
}
.content h3 {
	text-transform: uppercase;
	margin: 0;
	letter-spacing: 3px;
	font-size: 20px;
}
.content p {
	margin: 10px 0;
}
.content p.iconed {
	display: flex;
	align-items: center;
	img {
		width: 16px;
		height: 16px;
		margin-right: 5px;
	}
}
.content .exp h4 {
	margin-top: 10px;
	margin-bottom: 0;
}
.content .exp p.info {
	margin: 0;
	color: @black;
	font-style: italic;
}
.content .exp p.description {
	margin-top: 0;
}
@media screen and (max-width: 788px){
	#home {
		flex-direction: column;
	}
	#home #left_content {
		width: 100%;
		flex-direction: row;
		padding: 15px 20px;
		flex-wrap: wrap;
		height: auto;
		justify-content: space-between;
	}
	#home #left_content #profile_picture {
		margin-top: 0;
		align-self: unset;
		width: 120px;
	}
	#home #left_content .content {
		margin: 0;
		display: table;
	}
	.content p {
		margin: 0;
		&:first-of-type {
			margin-top: 10px;
		}
		&:last-of-type  {
			margin-top: 5px;
		}
	}
	#home #right_content {
		width: 100%;
		padding: 0 20px 30px 20px;
	}
	#home #right_content #description {
		margin-top: 30px;
	}
}
@media screen and (max-width: 700px){
	#home #left_content {
		flex-direction: row;
		flex-wrap: wrap;
	}
	#home #left_content .content {
		width: 50%;
		text-align: right;
		&:first-of-type {
			margin-bottom: 20px;
			display: flex;
			flex-direction: column;
			align-items: flex-end;
		}
		&:nth-of-type(2){
			text-align: left;
		}
	}
	#home #left_content #profile_picture {
		margin-bottom: 20px;
	}
}
@media screen and (max-width: 450px){
	#home #left_content {
		flex-direction: row;
	}
	#home #left_content .content {
		margin-bottom: 20px;
	}
}

@media screen and (max-width: 374px){
		#home #left_content {
		flex-direction: column;
	}
	#home #left_content .content {
		text-align: left;
		&:first-of-type {
			align-items: flex-start;
		}
	}
}
</style>
