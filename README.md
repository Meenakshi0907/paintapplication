# Web Page for Paint Application

## AIM:

To design a static website for Paint Application using HTML5 canvas.

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML,CSS and canvas.

### Step 3:

Write javascript to capture move events.

### Step 4:

Perform the drawing operation based on the user input.

### Step 5:

Validate the layout in various browsers.

### Step 6:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
~~~
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Paint Application of Karthi sir student </title>
    <link rel="icon" href="./img/obed sir.jpg" type="image/x-icon" />
    <body id="bgimg">
        <div class="container">
          <div class="da">
            <div class="text">
          <center>
            <marquee behavior="scroll" direction="left" scrollamount="12"><h1>Paint Application  Designed  by
                
                      MEENAKSHI M</h1><br>
            </marquee>
            </center> 
        </div>
        </div>
    <style>
    #content{
    margin-left: 650px;
    margin-right: 550px;
      }

        #myCanvas{
          background-color: #ecea77;
          box-shadow: inset 0 0 5px #141313; 
          border-radius: 2px;
          border: 5px solid #000000;
        }
        #buttonstyle{
          background-color: #eea968;
          border: 2px solid #130a0900;
          border-radius: 5px;
          color: rgb(24, 24, 24);
          padding: 12px 12px;
          text-align: center;
          display: inline-block;
          font-size: 20px;
          margin: 3px 4px;
          cursor: pointer;
        }
        #buttonstyle:hover{
            background-color:#9de9f3;
            transition: 0.5s;
        }
        #bgimg{
            background-image:url("/static/img/captain america 3.png");
        }
        #shooky{
            border: 2px solid #0a020200;
            border-radius: 25px;
            padding: 25px 25px;
            text-align: center;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
        }
        #shooky:hover{
            opacity: 20%;
            transition: 0.21s;
        }
        </style>
  </head>
  <body id="bgimg">
    <div id="content">
      <canvas id="myCanvas" width="600" height="800" onclick="showCoords(event)"></canvas></div>
      <center>
      <button onclick="shape=1" id="buttonstyle" >Solid Circle</button>
      <button onclick="shape=2" id="buttonstyle">circle</button>
      <button onclick="shape=3" id="buttonstyle">Solid Square</button>
      <button onclick="shape=4" id="buttonstyle">Square</button>
      <button onclick="shape=5" id="buttonstyle">Solid Triangle</button>
      <button onclick="shape=6" id="buttonstyle">Triangle</button>
      <br>
      <button onclick="size()" id="buttonstyle" >Change size</button></center>
      <center>
      <button onclick="change_color(this)" id="shooky" style="background: white;"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(255, 72, 72);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(255, 115, 1);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(252, 255, 60);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(94, 255, 45);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(7, 184, 1);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(49, 231, 255);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(46, 112, 255);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(213, 76, 255);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(153, 0, 255);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(54, 0, 124);"></button>
      <button onclick="change_color(this)" id="shooky" style="background: rgb(0, 0, 0);"></button>
      </center>

      <script>


        const canvas = document.getElementById("myCanvas");
        const ctx = canvas.getContext("2d");
        ctx.fillStyle = "#FF0000";
        canvas.height = canvas.width;
        ctx.transform(1, 0, 0, -1, 0, canvas.height);
        let xMax = canvas.height;
        let yMax = canvas.width;
        let csize= 20;
        let sqsize= 50;
        let tsize=50;
        let tata="black";
        function size(){   
          if (shape==1 ||shape==2){
            let c= prompt("Please enter size of circle", "ex:100,50");
            csize=c;
          } 
          if (shape==3 ||shape==4){
            let s = prompt("Please enter size of square", "ex:100,20");
            sqsize=s;
          }
          if (shape==5 || shape==6){
            let t= prompt("Please enter size of triangle","ex:50,84");
            tsize=t;
          }
        }
        function change_color(element){
          tata=element.style.background;
        }
        function showCoords(event)
        {
          var x = event.clientX-545;
          var y = yMax-event.clientY;
          var coords = "X coords: " + x + ", Y coords: " + y;
          document.getElementById("demo").innerHTML = coords;
    
          if (shape==1){
            ctx.beginPath();
            ctx.arc(x, y, csize, 0, 2 * Math.PI);
            ctx.fillStyle=tata;
            ctx.fill();
          }
          if (shape==2){
            ctx.beginPath();
            ctx.arc(x, y, csize, 0, 2 * Math.PI);
            ctx.strokeStyle=tata;
            ctx.stroke();
          }
          if (shape==3){
            ctx.beginPath();
            ctx.rect(x-(sqsize/2),y-(sqsize/2), sqsize,sqsize);
            ctx.fillStyle=tata;
            ctx.fill();
          }
          if (shape==4){
            ctx.beginPath();
            ctx.rect(x-(sqsize/2),y-(sqsize/2), sqsize,sqsize);
            ctx.strokeStyle=tata;
            ctx.stroke();
          }
          if (shape==6){
            ctx.beginPath();
            ctx.moveTo(x, y);
            ctx.lineTo(x-(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x+(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x,y)
            ctx.strokeStyle=tata;
            ctx.stroke();
          }
          if (shape==5){
            ctx.beginPath();
            ctx.moveTo(x, y);
            ctx.lineTo(x-(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x+(tsize/2),y-(tsize*0.86602));
            ctx.fillStyle=tata;
            ctx.fill();
          }    
        }
      </script>
    <center><p id="demo" style="color: white;"></p></center>
    <p 
    style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif; 
    text-align: center;
    color:rgb(8, 8, 8);
    font-weight: bold;
    font-size: larger;">PAINT APPLICATION DEVELOPED BY<br>MEENAKSHI M</p> 
     <br>
  </body>
</html>
~~~
## OUTPUT:

![output](./canvas.png)

## Result:

Thus a website is designed and validated for paint application using HTML5 canvas.
