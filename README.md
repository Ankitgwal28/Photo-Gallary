<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Photo Gallery</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#f4f4f4;
}

header{
    background:linear-gradient(45deg,#6a11cb,#2575fc);
    color:white;
    text-align:center;
    padding:25px;
}

header h1{
    font-size:40px;
}

.gallery{
    width:90%;
    margin:30px auto;
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:20px;
}

.gallery img{
    width:100%;
    height:250px;
    object-fit:cover;
    border-radius:12px;
    cursor:pointer;
    transition:0.4s;
    box-shadow:0 4px 10px rgba(0,0,0,0.2);
}

.gallery img:hover{
    transform:scale(1.05);
}

.lightbox{
    display:none;
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    background:rgba(0,0,0,0.9);
    justify-content:center;
    align-items:center;
}

.lightbox img{
    max-width:80%;
    max-height:80%;
    border-radius:10px;
}

.close{
    position:absolute;
    top:20px;
    right:30px;
    color:white;
    font-size:40px;
    cursor:pointer;
}

footer{
    text-align:center;
    background:#222;
    color:white;
    padding:15px;
    margin-top:20px;
}
</style>
</head>
<body>

<header>
    <h1>My Photo Gallery</h1>
    <p>Beautiful Memories Collection</p>
</header>

<div class="gallery">
    <img src="https://picsum.photos/id/1015/600/400" onclick="openImage(this.src)">
    <img src="https://picsum.photos/id/1025/600/400" onclick="openImage(this.src)">
    <img src="https://picsum.photos/id/1035/600/400" onclick="openImage(this.src)">
    <img src="https://picsum.photos/id/1045/600/400" onclick="openImage(this.src)">
    <img src="https://picsum.photos/id/1055/600/400" onclick="openImage(this.src)">
    <img src="https://picsum.photos/id/1065/600/400" onclick="openImage(this.src)">
</div>

<div class="lightbox" id="lightbox">
    <span class="close" onclick="closeImage()">&times;</span>
    <img id="lightbox-img">
</div>

<footer>
    <p>© 2026 My Photo Gallery | Designed with HTML, CSS & JavaScript</p>
</footer>


<script>
function openImage(src){
    document.getElementById("lightbox").style.display="flex";
    document.getElementById("lightbox-img").src=src;
}

function closeImage(){
    document.getElementById("lightbox").style.display="none";
}
</script>

</body>
</html>
