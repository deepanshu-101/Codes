# Codes
//Bubble game
<!DOCTYPE html>
<html>
<head>
   <title>bubble</title>
   <style>
    *{
     margin:0px;
     padding:0px;
     }
   body{
     width:100%;
     height:100%;
     background-color:green;
     display:flex;
     justify-content:center;
     align-items: center;
     }
   #main{
    width: 80%;
    height:50vh;
    border:2px solid black;
    
     }
   #mhd{
    width:100%;
    height:50px;
    background-color:lightblue;
    display:flex;
    align-items:center;
    justify-content:space-between;
    
     }
     
   .elem{
     padding:3px;
     width:25%;
     display:flex;
     align-items: center;
     }
   .box{
     background-color:white;
     border:1px solid black;
     height:20px;
     width:20px;
     text-align:center;
     }

   #mbtm{
    width:100%;
    height:287px;
    background-color:white;
    display:flex;
    flex-wrap:wrap;
    align-items:center;
    justify-content:center;
     }

   .bubble{
    height:20px;
    width:20px;
    border-radius:50%;
    border: 1px solid green;
    background-color:green;
    color:white;
    text-align:center;
    margin:2px
     }

   .bubble:hover{
     background-color:lightgreen;
     color:black
     }
   </style>
</head>
<body>
   <div id="main">
     <div id="mhd">
       <div class="elem">
         <h5>HIT</h5>
         <div id="hit" class="box"></div>
       </div>
       <div class="elem">
         <h5>TIME</h5>
         <div id="time" class="box">60</div>
       </div>
       <div class="elem">
         <h5>SCORE</h5>
         <div id = "score" class="box">0</div>
       </div>
     </div>
     <div id="mbtm">
       
     </div>
   </div>

  <script>

    let score = 0;
    let vrn = 0;
    function CreateBubble(){
    var bubble="";
    for(let i=1; i<=132; i++){
      let rn = Math.floor(Math.random()*10);
      bubble += `<div class="bubble">${rn}</div>`;
    }
  document.querySelector("#mbtm").innerHTML = bubble;
     }

    function Time(){
      let timer = 60;
     let time = setInterval(function(){
        if(timer >0){
       timer--;
       document.querySelector("#time").innerHTML= timer;
        }else{
         document.querySelector("#mbtm").innerHTML = `Your Final Score : ${score}`
         clearInterval(time);
        }
      },1000) 
    }
    
    function Score(){
     score += 10;
     document.querySelector("#score").innerHTML=score;
}
  
  function Hit(){
    vrn = Math.floor(Math.random()*10);
    document.querySelector("#hit").innerHTML = vrn;
     }

  
  document.querySelector("#mbtm")
  .addEventListener("click", function(values){
    let store = Number(values.target.textContent);
    if(store === vrn){
     Score();
     Hit();
     CreateBubble();
   }
 
   });
    
  

  CreateBubble();
  Time();
 Hit();
  </script>


</body>
</html>
