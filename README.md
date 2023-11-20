/* Frame */

.wrap{
	max-width: 700px; /* Width of coverflow gallery. Should be in px. */
}

.frame {
	height: 250px; /* height of each item */
	line-height: 250px; /* height of each item */
	overflow: hidden;
}
.frame ul {
	list-style: none;
	margin: 0;
	padding: 0;
	height: 100%;
	font-size: 50px;
}
.frame ul li {
	float: left;
	width: 227px; /* width of each item */
	height: 100%;
	margin: 0 1px 0 0;
	padding: 0;
	background-position: center center; /* center image within carousel */
	background-repeat: no-repeat;
	background-size: cover; /* CSS3 property to scale image within container? "cover" or "contain" */
	color: #ddd;
	text-align: center;
	cursor: pointer;
}
.frame ul li.active {
	color: #fff;
}

/* Scrollbar */
.scrollbar {
	margin: 0 0 1em 0;
	height: 3px;
	background: #ccc;
	line-height: 0;
}
.scrollbar .handle {
	width: 100px;
	height: 100%;
	background: #292a33;
	cursor: pointer;
}
.scrollbar .handle .mousearea {
	position: absolute;
	top: -9px;
	left: 0;
	width: 100%;
	height: 20px;
}

/* Pages */
.pages {
	list-style: none;
	margin: 20px 0;
	padding: 0;
	text-align: center;
}
.pages li {
	display: inline-block;
	width: 14px;
	height: 14px;
	margin: 0 4px;
	text-indent: -999px;
	border-radius: 10px;
	cursor: pointer;
	overflow: hidden;
	background: #fff;
	box-shadow: inset 0 0 0 1px rgba(0,0,0,.2);
}
.pages li:hover {
	background: #aaa;
}
.pages li.active {
	background: #666;
}

/* Coverflow effect. .no-ie applies only to non IE browsers. See .js file for filter used */
.no-ie .coverflow {
	-webkit-perspective: 800px;
	-ms-perspective: 800px;
	perspective: 800px;
	-webkit-perspective-origin: 50% 50%;
	-ms-perspective-origin: 50% 50%;
	perspective-origin: 50% 50%;
	overflow-y: show;
}

.no-ie .coverflow ul {
	-webkit-transform-style: preserve-3d;
	-ms-transform-style: preserve-3d;
	transform-style: preserve-3d;
}

.no-ie .coverflow ul li {
	position: relative;
	margin: 0 -20px;
	-webkit-transform: rotateY(60deg) scale(0.9);
	-ms-transform: rotateY(60deg) scale(0.9);
	transform: rotateY(60deg) scale(0.9);
	-webkit-transition: -webkit-transform 300ms ease-out;
	transition: transform 300ms ease-out;
}

.no-ie .coverflow ul li.active {
	z-index: 10;
	-webkit-transform: scale(1);
	-ms-transform: scale(1);
	transform: scale(1);
}

.no-ie .coverflow ul li.active ~ li {
	-webkit-transform: rotateY(-60deg) scale(0.9);
	-ms-transform: rotateY(-60deg) scale(0.9);
	transform: rotateY(-60deg) scale(0.9);
}

/* Overlay effect */

#coverflowoverlay{
	position: fixed;
	width: 100%;
	height: 100%;
	opacity: 0;
	background: gray;
	left: 0;
	top: 0;
	z-index: -1;
}

#coverenlargearea{
	position: fixed;
	left: 50%;
	top: 50%;
	max-width: 95%;
	height: auto;
	-ms-transform: translate(-50%, -50%);
	-webkit-transform: translate(-50%, -50%);
	transform: translate(-50%, -50%);
	opacity: 0;
	background: white;
	z-index: -1;
	transition: all .2s ease-in;
}

#coverenlargearea img{
	/* max-width value set by script dynamically, due to some mobile issues otherwise */
	/* max-height value set by script dynamically, due to some mobile issues otherwise */
	display: block;
}

#coverenlargearea #desc{
	position: absolute;
	bottom: 0;
	background: white;
	padding: 4px;
	width: 100%;
	-webkit-box-sizing: border-box;
	-moz-box-sizing: border-box;
	box-sizing: border-box;
	font-size: 120%;
}
