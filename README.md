# Polindrama
package main;
import java.util.Scanner;

public class Polindrama {
	
	
	/*
	 * Far inserire all'utente una parola di almeno 3 lettere, 
	 * una volta premuto il tasto invio, dirgli se è palindroma o no;
	 */

	
	public static void main(String[] args) {
		Scanner in= new Scanner(System.in);
		
		System.out.println("Inserire valore da controllare se sia Palindroma:");
		String parola = in.nextLine();
		
//		il metodo statico isPalindroma che restituirà 
//	 * il valore true se l'input inserito dall'utente è palindromo, 
//	 * false altrimenti */
		
		boolean Palindroma = ePalindroma(parola);
		
		if(Palindroma){
			System.out.println("La parola/frase/numeri '"+parola+"' è Palindrima");			
		}else{
			System.out.println("La parola/frase/numeri '"+parola+"' Non è Palindrima");		
		}
	}
	
	/*
	   Metodo statico 

	     public static boolean isPalindroma(String word)

	   che data una variabile di tipo string chiamata 'word' restituisca 
	   un valore booleano vero se e solo se 'word' e' palindroma 
	   falso altrimenti. Una stringa e' palindroma se
	   può essere letta da sinistra verso destra e da destra verso
	   sinistra indifferentemente (es. "anna", "ailatiditalia", ecc.).
	*/
	public static boolean ePalindroma(String parola) {
		if(parola == null) 
			return false;
		
		/*Trasformo le lettere in 
		  minuscolo */
		
		parola = parola.toLowerCase().replaceAll("\\s", "");
		
		//Se la parole è di un solo carattere allora sarà sicuramente palindroma
		if(parola.length() < 2)  
		    return true;
		
		
		boolean palindroma = true;
		int startIndex = 0;
		int endIndex = parola.length()-1;
		
		/* Uso due indici uno che parte dalla prima posizione e verrà 
		   incrementato di uno ad ogni iterazione e un'altro indice che parte 
		   dall'ultima posizione della frase e verrà decrementato di uno
		   ad ogni iterazione*/
		for(; startIndex < endIndex; startIndex++, endIndex-- ) {
			/* Ad ogni iterazione controllo i due valori che si 
			   trovano nelle posizioni puntate dai due indici.
			   Se sono diversi il contenuto di 'word' non sarà palindroma */
			if(parola.charAt(startIndex) != parola.charAt(endIndex)) {
				palindroma = false;
				break;
			}
		}
		
		return palindroma;
	}

} 
