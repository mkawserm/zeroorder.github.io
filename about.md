---
title: About
layout: page
---
![Profile Image]({{ site.url }}/{{ site.picture }})

<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>


<!DOCTYPE html>
<meta charset="utf-8">
<style>
.mainBars rect{
  shape-rendering: auto;
  fill-opacity: 0;
  stroke-width: 0.9px;
  stroke: rgb(0, 0, 0);
  stroke-opacity: 0;
}
.subBars{
	shape-rendering:crispEdges;
}
.edges{
	stroke:none;
	fill-opacity:0.8;
}
</style>
<body>
<script src="https://d3js.org/d3.v4.min.js"></script>
<script src="http://vizjs.org/viz.v1.1.0.min.js"></script>
<script>


var data=[['Action','fear',1,1],
['Action','joy',1,1],
['Action','joy',1,1],
['Action','joy',1,1],
['Action','sadness',1,1],
['Action','sadness',1,1],
['Action','sadness',1,1],
['Action','sadness',1,1],
['Action','sadness',1,1],
['Adventure','joy',1,1],
['Adventure','sadness',1,1],
['Adventure','sadness',1,1],
['Adventure','sadness',1,1],
['Animation','joy',1,1],
['Biography','joy',1,1],
['Biography','sadness',1,1],
['Biography','sadness',1,1],
['Comedy','fear',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','joy',1,1],
['Comedy','sadness',1,1],
['Comedy','sadness',1,1],
['Comedy','sadness',1,1],
['Comedy','sadness',1,1],
['Comedy','sadness',1,1],
['Comedy','sadness',1,1],
['Comedy','sadness',1,1],
['Comedy','sadness',1,1],
['Crime','joy',1,1],
['Crime','joy',1,1],
['Crime','joy',1,1],
['Crime','sadness',1,1],
['Crime','sadness',1,1],
['Crime','sadness',1,1],
['Crime','sadness',1,1],
['Crime','sadness',1,1],
['Crime','sadness',1,1],
['Crime','sadness',1,1],
['Crime','sadness',1,1],
['Documentary','anger',1,1],
['Documentary','sadness',1,1],
['Documentary','sadness',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','joy',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Drama','sadness',1,1],
['Fantasy','fear',1,1],
['Fantasy','sadness',1,1],
['Fantasy','sadness',1,1],
['Fantasy','sadness',1,1],
['History','joy',1,1],
['History','sadness',1,1],
['History','sadness',1,1],
['History','sadness',1,1],
['Horror','sadness',1,1],
['Horror','sadness',1,1],
['Musical','sadness',1,1],
['Mystery','joy',1,1],
['Mystery','sadness',1,1],
['Mystery','sadness',1,1],
['Mystery','sadness',1,1],
['News','anger',1,1],
['Reality-TV','sadness',1,1],
['Romance','joy',1,1],
['Romance','joy',1,1],
['Romance','joy',1,1],
['Romance','joy',1,1],
['Romance','sadness',1,1],
['Romance','sadness',1,1],
['Romance','sadness',1,1],
['Romance','sadness',1,1],
['Sci-Fi','joy',1,1],
['Sci-Fi','joy',1,1],
['Sci-Fi','sadness',1,1],
['Short','joy',1,1],
['Sport','sadness',1,1],
['Sport','sadness',1,1],
['Talk-Show','sadness',1,1],
['Thriller','joy',1,1],
['Thriller','joy',1,1],
['Thriller','joy',1,1],
['Thriller','joy',1,1],
['Thriller','joy',1,1],
['Thriller','sadness',1,1],
['Thriller','sadness',1,1],];
var color ={Action:"#3366CC", Thriller:"#DC3912",  Romance:"#FF9900" , Comedy: "#F11199", Drama: "#959b1d", Crime: "#DD3211", History: "#1d9b5a", Mystery: "#91531d", Adventure:"#db0f23", Fantasy: "#510828"};
var svg = d3.select("body").append("svg").attr("width", 960).attr("height", 800);
var g = svg.append("g").attr("transform","translate(200,50)");

var bp=viz.bP()
		.data(data)
		.min(15)
		.pad(1)
		.height(600)
		.width(480)
		.barSize(35)
		.fill(d=>color[d.primary]);

g.call(bp);

g.selectAll(".mainBars")
	.on("mouseover",mouseover)
	.on("mouseout",mouseout)

g.selectAll(".mainBars").append("text").attr("class","label")
	.attr("x",d=>(d.part=="primary"? -30: 30))
	.attr("y",d=>+6)
	.text(d=>d.key)
	.attr("text-anchor",d=>(d.part=="primary"? "end": "start"));

g.selectAll(".mainBars").append("text").attr("class","perc")
	.attr("x",d=>(d.part=="primary"? -120: 80))
	.attr("y",d=>+6)
	.text(function(d){ return d3.format("0.0%")(d.percent)})
	.attr("text-anchor",d=>(d.part=="primary"? "end": "start"));

function mouseover(d){
	bp.mouseover(d);
	g.selectAll(".mainBars")
	.select(".perc")
	.text(function(d){ return d3.format("0.0%")(d.percent)})
}
function mouseout(d){
	bp.mouseout(d);
	g.selectAll(".mainBars")
		.select(".perc")
	.text(function(d){ return d3.format("0.0%")(d.percent)})
}
d3.select(self.frameElement).style("height", "800px");
</script>
</body>
</html>
LICENSE


<h2>Skills</h2>

<ul class="skill-list">
	<li>HTML - Jade - Haml - Erb</li>
	<li>Responsive (Mobile First)</li>
	<li>CSS (Stylus, Sass, Less)</li>
	<li>Css Frameworks (Bootstrap, Foundation)</li>
	<li>Javascript (Design Patterns, Testes)</li>
	<li>NodeJS</li>
	<li>AngularJS - ReactJS</li>
	<li>Grunt - Gulp - Yeoman</li>
	<li>Git</li>
	<li>PHP</li>
	<li>Python</li>
	<li>MySQL - MongoDB</li>
	<li>Scrum and Kanban</li>
	<li>TDD e Continuous Integration</li>
</ul>

<h2>Projects</h2>

<ul>
	<li><a href="https://github.com/">Lorem Lorem</a></li>
	<li><a href="https://github.com/">Ipsum Dolor</a></li>
	<li><a href="https://github.com/">Dolor Lorem</a></li>
</ul>
