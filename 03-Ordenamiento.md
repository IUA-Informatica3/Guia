![IUA Logo](/logo-iua.png)

# Práctico 3: **Ordenamiento**

1. Implemente los métodos de ordenamiento de **inserción**, **Shellsort** y **quicksort** usando las implementaciones del teórico. Ejecútelos con los siguientes objetos:

    1. Enteros.
    2. Números reales de tipo double.
    3. Cadena de caracteres.

2. Utilice los métodos de ordenación creados para ordenar los siguientes 3 archivos y evaluae el tiempo que demora cada algoritmo en cada caso.

| Archivo    | Descrpición | Inserción | Shellsort | Quicksort |
|------------|-------------|-----------|-----------|-----------|
| es.txt.gz  | desordenado |           |           |           |
| eso.txt.gz | ordenado    |           |           |           |
| esi.txt.gz |orden inverso|           |           |           |


### Anexo

Código de ejemplo para la lectura de archivos gz y medición de tiempo:
```java
import java.io.*;
import java.nio.charset.StandardCharsets;
import java.util.zip.GZIPInputStream;

public class ej1 {
    public static void main(String[] args) {
        String filename = "es.txt.gz";
        String line;
        try {
            InputStream gzStream = new GZIPInputStream(new FileInputStream(filename));
            BufferedReader br = new BufferedReader(new InputStreamReader(gzStream, StandardCharsets.UTF_8));

            long start = System.currentTimeMillis(); // para medir el tiempo de ejecución
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            System.out.println("demora: " + (System.currentTimeMillis() - start) + "ms");

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

```