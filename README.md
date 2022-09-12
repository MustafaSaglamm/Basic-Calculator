# calculator

!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    
<div class="Page">
    <h1>Calculator</h1>
    <table>
<tr>
    <td colspan="5" id="islem"></td>
</tr>
<tr>
    <td colspan="5" id="gosterge">0</td>
</tr>

<tr>
    <td class="btn btnNumber">7</td>
    <td class="btn btnNumber">8</td>
    <td class="btn btnNumber">9</td>
    <td class="btn btnOpt">/</td>
    <td class="btn btnCE">CE</td>
</tr>

<tr>
    <td class="btn btnNumber">4</td>
    <td class="btn btnNumber">5</td>
    <td class="btn btnNumber">6</td>
    <td class="btn btnOpt">*</td>
    <td class="btn btnC">C</td>
</tr>

<tr>
    <td class="btn btnNumber">1</td>
    <td class="btn btnNumber">2</td>
    <td class="btn btnNumber">3</td>
    <td class="btn btnOpt">-</td>
    <td rowspan="2" class="btn btnOpt">=</td>
</tr>

<tr>
    <td colspan="2" class="btn btnNumber">0</td>
    <td class="btn">.</td>
    <td class="btn btnOpt">+</td>
    
</tr>





    </table>
</div>

<script>

var optDurum=false,opt="",sonuc=0;

var btnNumber=document.querySelectorAll(".btnNumber");
var gosterge=document.querySelector("#gosterge");
var btnOpt=document.querySelectorAll(".btnOpt");
var islem=document.querySelector("#islem");
var btnC=document.querySelector(".btnC");
var btnCE=document.querySelector(".btnCE");

btnNumber.forEach(function(element){

element.onclick=function(e){

if(gosterge.textContent=="0" || optDurum)
gosterge.textContent="";



    gosterge.textContent+=this.textContent;
    optDurum=false;

}
});

btnOpt.forEach(function(element){

    element.onclick=function(e){
optDurum=true;
var yeniOpt=this.textContent;

islem.textContent=islem.textContent+" "+gosterge.textContent+" "+yeniOpt;
    

switch(opt)
{
    case "+":gosterge.textContent=(sonuc + Number(gosterge.textContent)); break;
    case "-":gosterge.textContent=(sonuc - Number(gosterge.textContent)); break;
    case "*":gosterge.textContent=(sonuc * Number(gosterge.textContent)); break;
    case "/":gosterge.textContent=(sonuc / Number(gosterge.textContent)); break;
    default:break;
}

sonuc=Number(gosterge.textContent);
opt=yeniOpt;

}
}
);



btnC.onclick=function(e){
gosterge.textContent="0";
}

btnCE.onclick=function(e){
gosterge.textContent="0";
islem.textContent="";
sonuc=0;
opt="";
}

</script>


</body>
</html>
