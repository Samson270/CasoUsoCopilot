# CasoUsoCopilot
Mostro un caso d'uso di Copilot

Nel prossimo esempio verrà evidenziata la capacità di Copilot di ottimizzare il codice e di come interviene nella creazione di test.
public class Calcoli {

    public int factorial(int n) {
        if (n == 0) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }

}

La classe “Calcoli.java” contiene un solo metodo utile per calcolare il fattoriale di un numero, tramite una semplice implementazione ricorsiva, che tuttavia potrebbe non essere ottimizzata in termini di performance. Chiedendo a Copilot di Ottimizzare la funzione otterremo: 
public class Calcoli {

    public int factorial(int n) {
        int result = 1;
        for (int i = 1; i <= n; i++) {
            result *= i;
        }
        return result;
    }

}

Nell’esempio proposto, l’ottimizzazione è stata applicata nella conversione della funzione ricorsiva originale per il calcolo del fattoriale in una versione iterativa. La versione ricorsiva calcola il fattoriale di un numero “n” chiamando sé stessa ricorsivamente fino a quando “n” raggiunge 0. La versione iterativa invece utilizza un ciclo for per iterare da 1 a “n”, moltiplicando ogni numero incontrato nel percorso. Questo approccio è più efficiente in termini di spazio e tempo rispetto all’approccio ricorsivo, specialmente per valori di “n” grandi, poiché evita la ricorsione e l’accumulo della pila di chiamate ricorsive.
In breve, l’ottimizzazione consiste nell’eliminare la ricorsione e utilizzare invece un approccio iterativo, che può portare a un miglioramento delle prestazioni e a un utilizzo più efficiente delle risorse.

import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class CalcoliTest {
    @Test
    public void testFactorialWithPositiveNumber() {
        Calcoli calcoli = new Calcoli();
        int result = calcoli.factorial(5);
        assertEquals(120, result);
    }

    @Test
    public void testFactorialWithZero() {
        Calcoli calcoli = new Calcoli();
        int result = calcoli.factorial(0);
        assertEquals(1, result);
    }

    @Test
    public void testFactorialWithNegativeNumber() {
        Calcoli calcoli = new Calcoli();
        int result = calcoli.factorial(-5);
        assertEquals(1, result);
    }
}


Evidenziando il metodo “factorial”, e successivamente chiedendo a Copilot di generare degli Unit Test, il programma genererà automaticamente una classe, dove importerà il package di Junit e genererà delle chiamate al metodo factorial per verificarne la correttezza per diversi input, inclusi input negativi e limiti (ad esempio, input uguale a 0).
