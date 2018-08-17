<!DOCTYPE html>
<html>
  <head>
    <style>
      #myContain {
        height: 400px;
        width: 400px;
        position: relative;
        background: cornflowerblue;
      }  
      #myAnimate {
        height: 50px;
        width: 50px;
        position: absolute;
        background: yellow;
      }
      #myAnimaty {
        height: 50px;
        width: 50px;
        position: absolute;
        background: red;
        top: 350px;
      }
      #myBullet {
        height: 5px;
        width: 5px;
        position: absolute;
        background: grey;
        top: 372.5px;
        left: 22.5px;
      }
    </style>
  </head>
  <body> 
  <p>
    <button onClick="myMove()">Start</button>
    Press screen to Start, Tap movables to stop them tap both to win!     </p>
    <div id="myContain">
      <div id="myAnimate" onclick="myStopA()"></div>
      <div id="myAnimaty" onclick="myStopB()"></div>
      <div id="myBullet"></div>
    </div>
    <script>
    var stop = 0;
    var epos = 0;
    var ypos = 372.5;
    var xpos = 22.5;
    var pos = 0;
    var xv = 5;  
    var yv = 1;
    var pew = 1;
    function myMove() {
      var elem = document.getElementById("myAnimate");
      var play = document.getElementById("myAnimaty");
      var shot = document.getElementById("myBullet");
      if (stop == 0) {
        stop++;
        var id = setInterval(frame, 10);
        function frame() {  
          if (pos == 350) {
            xv/=-1;
            pos+=xv;
            elem.style.left = pos + 'px';
          } else if (pos == 0 && xv < 0) {
            xv/=-1;
            pos+=xv;
            elem.style.left = pos + 'px';   
          } else {
            pos+=xv;
            elem.style.left = pos + 'px';
          }
          if (epos == 350) {
            yv/=-1;
            epos+=yv;
            play.style.left = epos + 'px';
          } else if (epos == 0 && yv < 0) {
            yv/=-1;
            epos+=yv;
            play.style.left = epos + 'px';
          } else {
            epos+=yv;
            play.style.left = epos + 'px';
          }
          if (pew < 0) {
            if (xpos < 6) {
              
            }
            shot.style.top = xpos + 'px';
            xpos--;
          } else {
            shot.style.left = epos + 22.5 + 'px';            
          }
        }
      }  
    }  
    function myStopA() {
      if (stop >= 1 && xv >=1) {
        stop++;
        xv=0;
      }
    }
    </script>
  </body>
</html>
