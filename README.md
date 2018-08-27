<!DOCTYPE html>
<html>
<head>
	<title></title>
    <style>
    	.view{
          	margin:10px auto;
          	width: 1200px;
          	height: 600px;
          	background-color: #c0c0c0;
          	text-align: center;
          	line-height: 600px;
   		 }
    	.imgs{
              width: 1200px;
              height:120px;
              margin:10px auto;
    	}
    	.imgs img{
    		width: 100px;
    		height: 120px;
    		float: left;
    		margin-left: 10px;
    		margin-top: 10px;
    	}
    	.a{
            border: 1px solid red;
            width: 164px;
            height: 50px;
            margin: 20px auto;
            background-color: green;
            border-radius: 25px;
    	}
    	.b{
			border: 0px solid red;
            width: 80px;
            height: 50px;
            float: left;
            text-align: center;
            border-radius: 25px;
    	}
    	.c{
			border: 1px solid red;
            width: 80px;
            height: 50px;
            background-color: blue;
            border-radius: 25px;
    	}
    	.ff{
    		border: 1px solid red;
    		width: 300px;
    		height: 600px;
    		float: left;
    		background-color: #c0c0c0;
    		transition: all 2s;
    	}
    	.ff :hover{
    		transform: rotate(180deg);
    	}
    </style>
</head>
<body bgcolor="green">
    <select id="select_1" style="margin-left: 50px;width: 100px;" onchange="on_change(this)">
    	<option value="0">a</option>
    	<option value="b">b</option>
    	<option value="c">c</option>
    	<option value="3">d</option>
    </select>
    <select id="select_2" style="width: 100px">
    	
    </select>

	<div class="view">
		<img src="4.jpg" width="1200" height="600">
	</div>
	<div class="imgs">
		<img src="1.jpg" onclick="click_img(1);">
		<img src="5.jpg" onclick="click_img(5);">
		<img src="2.jpg" onclick="click_img(2);">
		<img src="3.jpg" onclick="click_img(3);">
		<img src="6.jpg" onclick="click_img(6);">
	</div>
	<div class="a">
		<div class="b" onclick="click1()">s</div>
		<div class="b" onclick="click2()">d</div>
		<div class="c" id="lol">
	</div>
	
	<script>
		window.onload=function(){
              e=1;
		}
		function on_change(obj){
			var select_2=document.getElementById("select_2");
			for(var i=select_2.length-1;i>=0;i--){
					select_2.remove(i);
				}
			if(obj.options[obj.selectedIndex].value=="b"){
				select_2.add(new Option("b-1","B-1"));
				select_2.add(new Option("b-2","B-2"));
				select_2.add(new Option("b-3","B-3"));
				select_2.options[1].selected=true;
			}
			if(obj.options[obj.selectedIndex].value=="c"){
				select_2.add(new Option("c-1","C-1"));
				select_2.add(new Option("c-2","C-2"));
				select_2.add(new Option("c-3","C-3"));
				select_2.options[2].selected=true;
			}
		}
		function click1(){
			    var v = document.getElementById("lol");
			    var h = document.getElementById("he");
                if(e>50){
					var i = setInterval(function(){
					e-=10;
					v.style.marginLeft=e+"px";
					if(e<10){
						clearInterval(i);
					}
					},10);
				}				
		}
		function click2(){
				var v = document.getElementById("lol");
				var h = document.getElementById("he");
                if(e<4){
					var i = setInterval(function(){
					e+=10;
					v.style.marginLeft=e+"px";
					if(e>71){
						clearInterval(i);
					}
					},10);
				}				
		}
			
		function click_img(n){
			var img=document.images[0];
			img.src=n+".jpg";
			var e= 0;			
            img.style.width="0px";
            img.style.height="0px";
			var i = setInterval(function(){
				e+=10;
				img.style.transform="rotate("+e+"deg)";
				img.style.width=e*10/3+"px";
                img.style.height=e*5/3+"px";
				if(e>350){
					clearInterval(i);
				}
			},100);
		} 	
	</script>
</body>
</html>
