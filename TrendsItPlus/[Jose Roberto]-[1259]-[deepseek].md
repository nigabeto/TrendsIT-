
1. **Receba** valores inteiros não negativos.
2. **Ordene** esses valores da seguinte forma:
   - **Coloque** primeiro os números pares em ordem crescente.
   - **Depois**, coloque os números ímpares em ordem decrescente.
3. **Leia** a entrada:
   - A primeira linha contém um número inteiro positivo **N** (1 < N <= 10^5), que indica quantos números virão a seguir.
   - As próximas **N** linhas contêm, cada uma, um número inteiro não negativo.
4. **Exiba** os números ordenados conforme o critério acima, um por linha.

**Exemplo de Entrada:**
```
10
4
32
34
543
3456
654
567
87
6789
98
```

**Exemplo de Saída:**
```
4
32
34
98
654
3456
6789
567
543
87
```

programa em C# que implementa a lógica 

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class URI {

    static void Main(string[] args) { 
        // Lê o valor de N
        int N = int.Parse(Console.ReadLine());

        // Verifica se N está dentro do intervalo válido
        if (N <= 1 || N > 100000) {
            Console.WriteLine("N deve ser um inteiro positivo no intervalo 1 < N <= 10^5.");
            return;
        }

        // Listas para armazenar números pares e ímpares
        List<int> pares = new List<int>();
        List<int> impares = new List<int>();

        // Lê os N números
        for (int i = 0; i < N; i++) {
            int numero = int.Parse(Console.ReadLine());

            // Separa os números em pares e ímpares
            if (numero % 2 == 0) {
                pares.Add(numero);
            } else {
                impares.Add(numero);
            }
        }

        // Ordena os pares em ordem crescente
        pares.Sort();

        // Ordena os ímpares em ordem decrescente
        impares.Sort((a, b) => b.CompareTo(a));

        // Exibe os números pares primeiro, seguidos pelos ímpares
        foreach (int par in pares) {
            Console.WriteLine(par);
        }
        foreach (int impar in impares) {
            Console.WriteLine(impar);
        }
    }
}
```

### Explicação do código:
1. **Leitura de N**:
   - O valor de **N** é lido e verificado para garantir que está no intervalo válido (1 < N <= 10^5).
   - Caso **N** esteja fora do intervalo, o programa exibe uma mensagem de erro e termina.

2. **Separação de pares e ímpares**:
   - Os números são lidos e separados em duas listas: uma para números pares e outra para números ímpares.

3. **Ordenação**:
   - Os números pares são ordenados em ordem crescente usando `pares.Sort()`.
   - Os números ímpares são ordenados em ordem decrescente usando `impares.Sort((a, b) => b.CompareTo(a))`.

4. **Exibição dos resultados**:
   - Primeiro, os números pares são exibidos em ordem crescente.
   - Depois, os números ímpares são exibidos em ordem decrescente.

### Exemplo de uso:
Se a entrada for:
```
10
4
32
34
543
3456
654
567
87
6789
98
```

A saída será:
```
4
32
34
98
654
3456
6789
567
543
87
```

Esse programa atende aos requisitos do problema e funciona corretamente para entradas válidas.