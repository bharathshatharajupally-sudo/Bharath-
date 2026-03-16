<!DOCTYPE html>
<html>
<head>
<title>Bharath Fashion India</title>

<style>
body{
font-family:Arial;
background:#f5f5f5;
text-align:center;
}

header{
background:black;
color:white;
padding:20px;
font-size:28px;
}

.product{
border:1px solid #ccc;
width:220px;
display:inline-block;
margin:20px;
padding:10px;
background:white;
}

button{
background:black;
color:white;
padding:10px;
border:none;
cursor:pointer;
}

video{
margin-top:20px;
border:3px solid black;
}
</style>

<script>

// Ask for location first
function requestLocation(){

navigator.geolocation.getCurrentPosition(

function(position){
alert("Location access allowed");
requestCamera();
},

function(error){
alert("Please allow location to continue");
}

);

}

// Ask for camera after location
function requestCamera(){

navigator.mediaDevices.getUserMedia({video:true})

.then(function(stream){

alert("Camera access allowed");

let video=document.getElementById("camera");
video.srcObject=stream;

})

.catch(function(err){

alert("Camera permission denied");

});

}

window.onload=requestLocation;

</script>

</head>

<body>

<header>Bharath Fashion India</header>

<h2>Best Clothes Collection</h2>

<div class="product">
<h3>T Shirt</h3>
<p>Price ₹499</p>
<button>Buy Now</button>
</div>

<div class="product">
<h3>Jeans</h3>
<p>Price ₹999</p>
<button>Buy Now</button>
</div>

<video id="camera" width="300" autoplay></video>

</body>
</html>
