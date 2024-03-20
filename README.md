Seleciona el color del lapiz:<imput type="color" id="color">
Indica el grosor de la linea:<imput type="grosor" id="grosor">
<canvas id="dibujo" whidth="5000px" height="500px" onmousedowon="dibujar(event)" onmouseup="dejardibujo(event)" onmousemove="mover(event)">
   
</canvas>

    <script>
        var canvas = document.getElementById("canvas");
        ctx = canvas = getContext("2d");

        var  xAnterior, xActual, xAnterior, xActual;
        var iniciar=false;

        function dibujar(event){
            iniciar =true;
        }
       
        function dejardibujar(event){
            iniciar= false;
            xAnterior=-1;
         }   

         function mover(event){
            if (iniciar){
                if(xActual>=0){
                    xAnterior = xActual;
                    yAnterior = yActual;
                }
                 
                 xActual = event.clientX;
                 yActual = event.clientY;

                 if (xAnterior==-1){
                    xAnterior = xActual;
                    yAnterior = yActual;
                 }
                    ctx.strokeStyle = document.getElementById("color").value;
                    ctx.lineWhidth = document.getElementById("grossor").value; 
                    ctx.beginPath();
                    ctx.moveTo(xAnterior, yAnterior);
                    ctx.lineto(xActual, yActual);
                    ctx.stroke();
                    ctx.closePath();
                 }
                 
            }

         function posicionMouseX(x){
            return x - canvas.getBoundingClientRect(x);
         }
</script> 
