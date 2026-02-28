package modularizacion;

import java.util.Scanner; // para la entrada y salida de datos
import java.util.Random; // genera numero aleatorio, lo usé en el apartado de adivina el numero
public class modularizacion{

	static Scanner scanner= new Scanner(System.in); // definida con static porque es global
	
	public static void main(String[] args) { // aqui comienza el main
	


		        int opcion;

		        do {
		            System.out.println("\n===== MENÚ PRINCIPAL =====");
		            System.out.println("1. Calculadora básica");
		            System.out.println("2. Validación de contraseña");
		            System.out.println("3. Número primo");
		            System.out.println("4. Suma de números pares");
		            System.out.println("5. Conversión de temperatura");
		            System.out.println("6. Contador de vocales");
		            System.out.println("7. Factorial");
		            System.out.println("8. Juego de adivinanza");
		            System.out.println("9. Paso por referencia");
		            System.out.println("10. Tabla de multiplicar");
		            System.out.println("0. Salir");
		            System.out.print("Seleccione opción: ");

		            opcion = leerEntero();

		            switch(opcion) {// break se utiliza para salir del bloque de codigo despues de haber ejecutado una de las opciones.
		                case 1: calculadora(); break;
		                case 2: validarPassword(); break;
		                case 3: numeroPrimo(); break;
		                case 4: sumaPares(); break;
		                case 5: conversionTemperatura(); break;
		                case 6: contadorVocales(); break;
		                case 7: factorial(); break;
		                case 8: juegoAdivinanza(); break;
		                case 9: pruebaIntercambio(); break;
		                case 10: tablaMultiplicar(); break;
		                case 0: System.out.println("SALIENDO DEL SISTEMA..."); break;
		                default: System.out.println("Opción inválida.");
		            }

		        } while(opcion != 0);
		    } /* aqui termina el main*/
	
	
	
	
//******************************************
		    // VALIDACIONES
//******************************************
		    static int leerEntero() {
		        while(true) {
		            try {
		                return Integer.parseInt(scanner.nextLine());
		            } catch(NumberFormatException e) {
		                System.out.print("Ingrese un número válido: ");
		            }
		        }
		    }

		    static double leerDouble() {
		        while(true) {
		            try {
		                return Double.parseDouble(scanner.nextLine());
		            } catch(NumberFormatException e) {
		                System.out.print("Ingrese un número válido: ");
		            }
		        }
		    }

		    
		    
		    
	//************************************************    
		    //  CALCULADORA BASICA
	//************************************************
		    
		    static void calculadora() {

		    	
		    	   System.out.println("\n     CALCULADORA BÁSICA ");
		    	   System.out.println("\n");
		    	     
		        System.out.print("Primer número: ");
		        double a = leerDouble();

		        System.out.print("Segundo número: ");
		        double b = leerDouble();

		        System.out.println("\n"); /*para que no se vea tan junto*/
		        
		        System.out.println("1.Sumar");
		        System.out.println("2.Restar");
		        System.out.println("3.Multiplicar");
		        System.out.println("4.Dividir");
		        System.out.print("Elija una opción : ");
		        int op = leerEntero();

		        
		        
		        switch(op) {
		            case 1: System.out.println("EL Resultado de la Suma Es : " + sumar(a,b)); 
		            break;
		            case 2: System.out.println("EL Resultado de la Resta Es : " + restar(a,b));
		            break;
		            case 3: System.out.println("EL Resultado de la Multiplicación Es : " + multiplicar(a,b));
		            break;
		            case 4:
		                if(b!=0)
		                    System.out.println("EL Resultado de la División Es : " + dividir(a,b));
		                else
		                    System.out.println("No se puede dividir entre 0.");
		                break;
		            default: System.out.println("Opción inválida.");
		        }
		    }

		    static double sumar(double a,double b){ return a+b; }
		    static double restar(double a,double b){ return a-b; }
		    static double multiplicar(double a,double b){ return a*b; }
		    static double dividir(double a,double b){ return a/b; }

		    
//*********************************************		    
		    //VALIDACION DE CONTRASENA
//*********************************************
		    
		    static void validarPassword() {//INDICA EL METODO QUE PERTENECE A LA CLASE EN SI Y ESPECIFICA EL TIPO DE RETORNO DEL METODO. 
		    	
		    	 System.out.println("\n     VALIDACIÓN DE CONTRASEÑA ");
		    	 System.out.println("\n");
		    	   
		    	 
		        String pass;//CREACION DE UNA VARIABLE PASS QUE ALMACENA UN VALOR DE TIPO STRING.
		        do {//ESTE BUCLE EJECUTA AL MENOS UNA VEZ ANTES DE EVALUAR LA CONDICION
		            System.out.print("Ingrese contraseña: ");
		            pass = scanner.nextLine();
		            if(!pass.equals("1234"))
		                System.out.println("Incorrecta.");
		        } while(!pass.equals("1234"));//EVALUA LA CONDICION ANTES DE EJECUTAR EL BLOQUE DE CODIGO
		        System.out.println("Acceso concedido.");
		    }
		    

		    
		    
//******************************************** 
		    // NUMEROS PRIMOS
//********************************************
		   
		    static void numeroPrimo() {
		    	
		    	
		    	 System.out.println("\n    NÚMEROS PRIMOS ");
		    	 System.out.println("\n");
		    	   
		    	 
		    	 
		        System.out.print("INGRESE EL NÚMERO: ");
		        int num = leerEntero();

		        if(esPrimo(num))
		            System.out.println("EL NÚMERO ES PRIMO");
		        else
		            System.out.println("EL NÚMERO NO ES PRIMO");
		    }

		    static boolean esPrimo(int num) {
		        if(num<=1) return false;
		        
		        for(int i=2;i<num;i++) {
		            if(num%i==0) return false;
		        }
		        return true;
		    }
		    
		    
//**************************************************
		    // SUMA DE NUMEROS PARES
//**************************************************
		    
		    static void sumaPares() {
		    	
		    	 System.out.println("\n     SUMA DE NÚMEROS PRIMOS ");
		    	 System.out.println("\n");
		    	   
		    	 
		        int suma=0;
		        int num;
		        
		        System.out.println("Ingrese números (0 para salir):");
		        
		        while((num=leerEntero())!=0) {
		            if(num%2==0) suma+=num;
		        }
		        System.out.println("Suma pares: "+suma);
		    }
		    
		    
		    
//*******************************************************
		    // CONVERSION DE TEMPERATURA
//*******************************************************
		    
		    static void conversionTemperatura() {
		    	
		    	 System.out.println("\n     CONVERSIÓN DE TEMPERATURA ");
		    	 System.out.println("\n");
		    	   
		    	 
		        System.out.println("1.Celsius a Fahrenheit");
		        System.out.println("2.Fahrenheit a Celsius");
		        System.out.println("Seleccione una opción :");
		        int op=leerEntero();
		        
		        System.out.print("Temperatura: ");
		        double t=leerDouble();

		        if(op==1)
		            System.out.println("Resultado: "+celsiusAFahrenheit(t));
		        else if(op==2)
		            System.out.println("Resultado: "+fahrenheitACelsius(t));
		        else
		            System.out.println("Opción inválida.");
		    }

		    static double celsiusAFahrenheit(double c){ return c*9/5+32; }
		    static double fahrenheitACelsius(double f){ return (f-32)*5/9; }
		    
		    
		    
		    
//**************************************************
		    // CONTADOR DE VOCALES
//**************************************************
		    
		    static void contadorVocales() {
		    	
		    	 System.out.println("\n     CONTADOR DE VOCALES ");
		    	 System.out.println("\n");
		    	   
		    	 
		        System.out.print("Ingrese un texto o palabra: ");
		        String texto=scanner.nextLine().toLowerCase();
		        
		        int contador=0;
		        for(int i=0;i<texto.length();i++) {
		            char c=texto.charAt(i);
		            if(c=='a'||c=='e'||c=='i'||c=='o'||c=='u')
		                contador++;
		        }
		        System.out.println("Cantidad de vocales: "+contador);
		    }

		    
		    
//***************************************************
		    // CALCULO DE FACTORIAL
//***************************************************
		    
		    static void factorial() {
		    	
		    	 System.out.println("\n     CÁLCULO DE FACTORIAL ");
		    	 System.out.println("\n");
		    	   
		        System.out.print("Ingrese número: ");
		        int num=leerEntero();
		        
		        if(num<0){
		            System.out.println("No negativo.");
		            return;
		        }
		        long resultado=1;
		        for(int i=1;i<=num;i++)
		            resultado*=i;
		        System.out.println("Factorial: "+resultado);
		    }

		    
		    
//***************************************************
		    //JUEGO DE ADIVINANZA 
//***************************************************
		    
		    static void juegoAdivinanza() {
		    	
		    	 System.out.println("\n     JUEGO DE ADIVINANZA ");
		    	 System.out.println("\n");
		    	   
		    	 
		        Random r=new Random();
		        int numero=r.nextInt(100)+1;
		        int intento;
		        do{
		            System.out.print("Adivine un número de 1 a 100: ");
		            intento=leerEntero();
		            
		            if(intento<numero) 
		            	System.out.println("Es Mayor");
		            
		            else if(intento>numero) System.out.println("Es Menor");
		        }while(intento!=numero);
		        System.out.println("¡ES CORRECTO!");
		    }
		    
		    
		    
//************************************************
		    // PASO POR REFERENCIA
//************************************************
		    
		    static void pruebaIntercambio() {
		    	
		    	 System.out.println("\n     PASO POR REFERENCIA ");
		    	 System.out.println("\n");
		    	   
		    	 
		        Numero a=new Numero(5);
		        Numero b=new Numero(10);

		        System.out.println("Antes: a="+a.valor+" b="+b.valor);
		        intercambiar(a,b);
		        System.out.println("Después: a="+a.valor+" b="+b.valor);
		    }

		    static void intercambiar(Numero x,Numero y){
		        int temp=x.valor;
		        x.valor=y.valor;
		        y.valor=temp;
		    }

		    
		    
		    
//******************************************************		    
		    // TABLA DE MULTIPLICAR 
//******************************************************
		    
		    static void tablaMultiplicar(){
		    	
		    	 System.out.println("\n     TABLA DE MULTIPLICAR ");
		    	 System.out.println("\n");
		    	   
		        System.out.print("Ingrese el número de tabla: ");
		        int n=leerEntero();
		        
		        for(int i=1;i<=10;i++)
		            System.out.println(n+" x "+i+" = "+(n*i));
		    }
		}



		class Numero{
		    int valor;
		    Numero(int valor){
		        this.valor=valor;
		    }
		}
