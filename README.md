<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>lunbo</title>
</head>
<body>
<style>
    #courBox{
        position: relative;
        height: 200px;
        width: 600px;
        margin: 0 auto;
        overflow: hidden;
    }
    #courBox img{
        height:200px;
        width:600px;
    }
    #courBox ul li{list-style: none;float: left;}
    #courBox ul{width: 3000px;position: absolute;left: 0;top: 0;margin: 0;padding: 0;}
    .tabTwo{position: absolute;top: 42%;width: 97%;padding: 0 10px;}
    .tabTwo a{text-decoration: none;color: white;font-size: 16px;background: rgba(185, 178, 178, 0.46);padding: 5px;}
    #prev{}
    #next{float: right;}
</style>
    <div id="courBox">
    		<ul class='tablist'>
    			<li>
        			<img src="img/1.jpg" alt="">
    			</li>
    			<li>
    				<img src="img/2.jpg" alt="">
    			</li>
    			<li>
    				<img src="img/3.jpg" alt="">
    			</li>
    		</ul>
    		
    		<div class="tabTwo">
    			<a href="javascript:;" id='prev'><</a>
    			<a href="javascript:;" id='next'>></a>
    		</div>
    </div>

<script src="js/jquery.js"></script>
    <script>
        
        $(function () {
        		 
        		 var index=1;
        		 var clone=$('#courBox li').eq(0).clone();
        		 var clonePre=$('#courBox li').eq(2).clone();
        		 $('.tablist').append(clone);
        		 $('.tablist').prepend(clonePre);
        		 $('.tablist').css('left','-600px');
        		 var size=$('#courBox li').length;
			 $('body').on('click','#next',function(){
			 	index++;
			 	if(index == size){
			 		$('.tablist').css('left','-600px');
			 		index=2;
			 	}
			 	$('.tablist').stop().animate({
			 		left:-index*600
			 	},500);
			 });
			 
			 $('body').on('click','#prev',function(){
			 	if(index == 0){
					$('.tablist').css('left',-(size-2)*600+'px');
			 		index=size-3;
			 	}else{
			 		index--;
			 	}
			 	$('.tablist').stop().animate({
			 		left:-index*600
			 	},500);
			 });
			 
			 setInterval(function(){
			 	$('#next').click();
			 },3000);
        })
        
    </script>
</body>
</html>
