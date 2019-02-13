# innocentmagumba.github.io

<!DOCTYPE html>
<html lang="en-US">
  
    
  
  
  
  
  
  
  
  
  
  
  
  
  
  %nav
	.mini
		%p.products Empty
		%p.names
		%p.miniprice
	%ul
		%li Home
		%li Webshop
		%li Contact
	.cart.icon-basket
		%span.number 1
.container
	-15.times do
		%div.product
			%img(src='https://placeimg.com/200/100')
			%h2.header Product Name
			%p.description Nullam posuere turpis vel lacinia luctus. Donec in efficitur neque. Curabitur consectetur non ipsum in eleifend. Praesent id velit in nisi maximus porta nec vitae odio. Proin vitae magna a massa accumsan venenatis. Donec semper, sem in ullamcorper bibendum, mauris sem imperdiet lorem, tempor aliquet ligula lorem sit amet nibh. Suspendisse potenti.
			%p.price 231,-
			.btn Add to cart
			.quickview Quickview
.quickviewContainer
	.close
	%h2.headline
	%p.description
	%img(src='https://placeimg.com/100/100')
	%img(src='https://placeimg.com/100/100')
	%img(src='https://placeimg.com/100/100')
	
	
	
	
	
	
	
	
	
	
	@import url(https://fonts.googleapis.com/css?family=Nunito:400,300,700);

$body:#0b0b0b;
$nav:#ffffff;
$contrast:#00fefe;
$contrastopacity: rgba(0,254,254, .4);
$productbg:rgba(255,255,255,.45);
$quickViewBg:rgba(0,0,0,.90);
$overlay:rgba(0,0,0,1);

* {
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	box-sizing: border-box;
}

body{
	background-color: $body;
	font-family: 'Nunito', sans-serif;
}

nav{
	position: fixed;
	z-index: 999;
	width: 100%;
	height: 70px;
	background-color: $nav;
	line-height: 70px;
	.mini{
		position: fixed;
		top: 80px;
		right:10px;
		background: #FFF;
		padding: 40px;
		opacity: 0;
		visibility: hidden;
		transition: opacity .2s ease .2s;
		&.visible{
			padding: 40px;
			opacity: 1;
			visibility: visible;
		}
		.products{
			font-weight: bold;
			font-size: 14px;
		}
		p{
			font-size: 11px;
			display:block;
			margin:0;
			padding: 0;
			line-height: 20px;
		}
	}
	.cart{
		position: relative;
		float: right;
		margin-right: 50px;
		height:20px;
		line-height: 70px;
		font-size: 28px;
		height: 100%;
		cursor: pointer;
		span{
			height: 100%;
			float: left;
			margin-right: 20px;
			opacity: 1;
			color: #fff;
			font-size: 18px;
			font-family: 'Nunito', sans-serif;
			
			&.updateQuantity{
				&:before, &:after{
					top: 0;
					bottom: 0;
					opacity: 1;
					width: 30px;
					transition: all .2s ease, top .3s ease .4s, bottom .3s ease .4s;
				}
			} 
			
			&.update{
				transition: color .2s ease .6s;
				color: #000;
				&:before{
					top: -30px;
					width: 30px;
					opacity: 1;
					transition: all .2s ease, top .3s ease .4s, bottom .3s ease .4s;
				}
				&:after{
					top: 30px;
					width: 30px;
					opacity: 1;
					transition: all .2s ease, top .3s ease .4s, bottom .3s ease .4s;
				}
			}
			&:before, &:after{
				content: "";
				position: absolute;
				width: 0px;
				height: 2px;
				background-color: $body;
				left: -10px;
				right:40px;
				top: 2px;
				bottom: 0;
				margin: auto;
			}
		}
	}
	ul{
		float: left;
		li{
			font-weight: bold;
			display: inline-block;
			margin-left: 50px;
			color: $body;
			font-size: 12px;
		}
	}
}

.container{
	padding: 20px;
	padding-top: 100px;
	text-align: center;
	.product{
		position: relative;
		overflow: hidden;
		width: 200px;
		height: 240px;
		display: inline-block;
		border-radius: 4px;
		background-color: $productbg;
		margin: 20px;
		padding: 15px;
		img{
			position: relative;
			top:-15px;
			left:-15px;
			transition: all .2s ease;
			clip-path: polygon(0 100%, 0 0, 100% 0, 100% 70%);
			border-top-right-radius: 4px;
			border-top-left-radius: 4px;
			&:hover{
				clip-path: polygon(0 100%, 0 0, 100% 0, 100% 100%);
				transform: scale(1.1);
			}
		}
		h2{
			text-align: left;
			color: #fff;
			font-size: 14px;
			font-weight: bold;
			margin-bottom: 4px;
		}
		.description{
			text-align:left;
			font-size: 11px;
			color: #fff;
			max-height: 23px;
			overflow: hidden;
		}
		.price{
			text-align: right;
			font-size: 18px;
			color: #fff;
			margin-top: 6px;
		}
		.btn{
			position: absolute;
			font-size: 11px;
			font-weight: bold;
			float: right;
			padding: 10px;
			border: 2px solid $contrast;
			border-radius: 20px;
			bottom: 10px;
			right: 10px;
			color: $contrast;
			cursor: pointer;
			overflow: hidden;
			transition: all .2s ease;
			&.ok{
				background-color: $contrastopacity;
				color: #fff;
				&:after{
					content:"\e080";
					color: #fff;
				}
			}
			&:hover{
				padding-right: 25px;
				
				&:after{
					margin-left: 5px;
				}
			}
			&:after{
				font-family: 'simple-line-icons';
				content: "\e095";
				transition: all .2s ease;
				position: absolute;
				color: $contrast;
				margin-left: 30px;
				transition: all .2s ease;
			}
		}
		.quickview{
			position: absolute;
			bottom: 20px;
			font-size: 11px;
			color: #fff;
			cursor: pointer;
			
			&:before{
				font-family: 'simple-line-icons';
				content: "\e05d";
				margin-right: 3px;
			}
		}
	}
}

.quickviewContainer{
	position: fixed;
	height: 100vh;
	width: 400px;
	background: $quickViewBg;
	top: 70px;
	right: -100%;
	transition: all .3s ease;
	padding: 30px;
	color: #fff;
	
	.close{
		height: 20px;
		width: 20px;
		float: right;
		cursor: pointer;
		&:before, &:after{
			content: "";
			position: absolute;
			width: 20px;
			height: 2px;
			background-color: #ffF;
			transform: rotate(45deg);
		}
		&:after{
			transform: rotate(-45deg);
		}
	}
	.headline{
		margin-bottom: 30px;
		font-size: 18px;
	}
	.description{
		font-size: 12px;
		margin-bottom: 20px;
	}
	img{
		display: inline-block;
		border-radius: 4px;
		margin:5px;
	}
	&.active{
		right:0;
	}
}










var cartCount = 0,
	 buy = $('.btn'),
	 span = $('.number'),
	 cart = $('.cart'),
	 quickview = $('.quickviewContainer'),
	 quickViewBtn = $('.quickview'),
	 close = $('.quickviewContainer .close'),
	 minicart = [],
	 totalPrice = [],
	 miniCartPrice;

buy.on('click', addToCart);
quickViewBtn.on('click', quickView);
cart.on('click', showMiniCart);
close.on('click', function(){
	quickview.removeClass('active');
});

function quickView() {
	var description = $(this).parent().find('.description').text(),
		 header = $(this).parent().find('.header').text(),
		 price = $(this).find('.price'),
		 quickViewHeader = $('.quickviewContainer .headline'),
		 quickViewDescription = $('.quickviewContainer .description');
	clearTimeout(timeQuick);
		if(quickview.hasClass('active')){
			quickview.removeClass('active');
			var timeQuick = setTimeout(function(){
				quickview.addClass('active');
			}, 300);
		} else{
			quickview.addClass('active');
		}
	
	quickViewHeader.text(header);
	quickViewDescription.text(description);
}

function showMiniCart() {
	$('.mini').toggleClass('visible');
}

function addToCart() {
	var self = $(this),
		 productName = $(this).parent().find('.header').text(),
		 miniCartNames = $('.products'),
		 names = $('.names'),
		 price = $(this).parent().find('.price').text(),
		 priceInt = parseInt(price);
	
	totalPrice.push(priceInt);
	miniCartPrice = totalPrice.reduce(function(a,b){  return a+b });
	$('.miniprice').text('Total amount: ' + miniCartPrice + ",-");
	minicart.push(productName);
	lastProduct = minicart[minicart.length - 1];
	miniCartNames.text('Your cart lines: ');
	names.append('<p>' + lastProduct + '</p>');
	
	cartCount++;
	span.text(cartCount);
	clearTimeout(time);
	if(span.hasClass('update')){
		span.removeClass('update');
		span.addClass('updateQuantity');
		var time = setTimeout(function(){
			span.removeClass('updateQuantity');
			span.addClass('update');
		}, 700);
	} else{
		span.addClass('update');
	}
	if (cartCount == 1){
		cart.toggleClass('icon-basket icon-basket-loaded');
	}
	
	$(this).addClass('ok');
	var timeOk = setTimeout(function(){
		self.removeClass('ok');
	}, 1000);
}






  
</html>
