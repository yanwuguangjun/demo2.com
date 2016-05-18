<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>demo</title>
		<link rel="stylesheet" type="text/css" href="css/css.css"/>
        <script src="http://libs.baidu.com/jquery/2.0.0/jquery.min.js"></script>
	</head>
	<body>
	  <div class="warp">	
		<ul class="ul_1">
			<li><a href=""><img src="img/18423942_9.jpg"/></a></li>
			<li><a href=""><img src="img/90fba60155890ed3082500.jpg"/></a></li>
		</ul>
		<ul class="ul">
			<li>1</li>
			<li>2</li>
		</ul>
		<div class="left"><</div>
		<div class="right">></div>
		
	  </div>	
	  <div class="img">
			<img src="img/12323.jpg"/>
			<img src="img/12342134.jpg"/>
		</div>
		<script type="text/javascript">
			$().ready(function(){
				$(".ul_1 li").eq(0).show();
				$(".ul li").eq(0).addClass("back")
				$(".ul li").mouseover(function(){
					$(this).addClass("back").siblings().removeClass("back");
					var index=$(this).index();
					$(".ul_1 li").eq(index).stop().fadeIn().siblings().stop().fadeOut();
				});
				var i=0
				var t=setInterval(move,3000);
				function move (){
					i++;
					if(i==2){
						i=0;
					}
					$(".ul li").eq(i).addClass("back").siblings().removeClass("back");
					$(".ul_1 li").eq(i).fadeIn().siblings().fadeOut();
				}
				
				$(".warp").hover(
					function(){clearInterval(t)},
					function(){
						t=setInterval(move,3000);
						}
				);
			});
		</script>
	</body>
</html>
