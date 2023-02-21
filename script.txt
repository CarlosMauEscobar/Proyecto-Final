 var salida = true;
do{
  var salida= true;
var precio_base= 2000; //precio del seguro sin recargos

var edad_18a24= 0.1; // recargo del 10%
var edad_25a49= 0.2; // recargo del 20%
var edad_50= 0.3; // recargo del 30%
  
var hijos= false;
var recargo_hijos= 0.2; // recargo que se realiza por cada hijo

var recargo1 = 0;
var recargo2=0;
var recargo3=0;
var recargo4=0;
var recargo5=0;
var recargo_final = 0;

var precio_final = 0;

var edad=0;

  //asegurado
  var nombre = prompt("Bienvenido al sistema de cotizaciones, por favor ingrese su nombre");
  var edad = prompt("Ingrese su edad, por favor","Ingresar el valor en digitos");
  
	if(edad<18){
   alert("Usted no es mayor de edad, no puede contrartar el servicio de aseguradora");
   break;
  } else{

  if (edad>=17&&edad<=24){
    var recargo1 = precio_base*0.1;
  }else if(edad>=25&&edad<=49){
    var recargo1 = precio_base*0.2;
  }else if(edad<=50){
    var recargo1 = precio_base*0.3;
  }
  alert(recargo1);
 //sueldo
  
  var sueldo = prompt("Por favor, ingrese el salario que usted gana","Ingrese el monto");
  
  var recargoSueldo = 0.05;
  
  var  recargo2 = sueldo*recargoSueldo;
  
  
  //propiedades
  var propiedades = prompt("¿Usted tiene propiedades?","Si/No");
  var propiedades = propiedades.toUpperCase();
  var confirmacionProp = "SI";
  var confirmacionPropF = (propiedades==confirmacionProp)?true:false;
  
  if(confirmacionPropF){
  	var cantidadPropiedades = prompt("Ingrese la cantidad de propiedades que tiene","Ingrese el digito");
    
    var recargoPropiedades = 0.35;
    var recargo5 = (precio_base*recargoPropiedades)*cantidadPropiedades;
  }else if(!confirmacionPropF){
  	var recargo5=0;
  }
  //Conyuge
  var estado= prompt("¿Usted está casado? (Si/No)","Si/no");
  var estado = estado.toUpperCase();
  var afirmacion = "SI";
  var confirmacion = (estado===afirmacion)?true:false;

 
  if (confirmacion){
  var edadPareja = prompt("¿Cuál es la edad de su esposa/o?");
  var edadPareja = parseInt(edadPareja);

   if (edadPareja>=18&&edadPareja<=24){
    var recargo3 = precio_base*0.1;
  }else if(edadPareja>=25&&edadPareja<=49){
    var recargo3 = precio_base*0.2;
  }else if (edadPareja>=50){
    var recargo3 = precio_base*0.3;
 }
  }else if(!confirmacion){
  	var recargo_final = recargo1;

  var precio_final = precio_base+recargo1;
  }else if(!confirmacion){
  	var recargo3 = 0;
  }

  //Hijos
  var familia = prompt("¿Usted tiene hijos?","Si/No");
  var familia = familia.toUpperCase();
  var familiaSi = "SI"

  var confirmacion1 = (familia===familiaSi)?true:false;

  var cantidad_de_hijos;
  if(confirmacion1){
    var cantidad_de_hijos= prompt("¿Cuantos hijos tiene?","Ingrese el valor en digitos");
    var integrantes = cantidad_de_hijos;
  	alert(integrantes);
  	var recargo4 = (precio_base * recargo_hijos)*integrantes;
   }else if(!confirmacion1){
      recargo4=0;
   }
	
  //Precio

  var recargo_final = recargo1+recargo2+recargo3+recargo4+recargo5;

  var precio_final = precio_base+recargo_final;

alert("La cotización para el asegurado: "+nombre);
alert("El total de los recargos es: "+recargo_final);
alert("el valor final de la cotización es: "+precio_final);

var verificacion = prompt("Si desea salir del programa, escriba Salir");
var salir = verificacion.toUpperCase();
var confirmacionsalida = "SALIR";

var salidaPrograma = (salir==confirmacionsalida)?true:false;
if(salidaPrograma){
var salida = false;
}else if(!salidaPrograma){
var salida = true;
}

	}
}while(salida);