
---

**Instruções:**

1. **Crie** uma pilha de cartas numeradas de **1** a **n**, com a carta **1** no topo e a carta **n** na base.
2. **Enquanto** houver **2 ou mais cartas** na pilha:
   - **Descarte** a carta do topo.
   - **Mova** a próxima carta (a que ficou no topo) para a base da pilha.
3. **Identifique** a sequência de cartas descartadas e a última carta que restou.
4. **Repita** o processo para cada valor de **n** fornecido na entrada.
5. **Pare** o processamento ao encontrar o valor **0** na entrada.

**Entrada:**
- **Leia** várias linhas, cada uma contendo um número **n** (onde **1 ≤ n ≤ 50**).
- A última linha contém **0** e não deve ser processada.

**Saída:**
- Para cada valor de **n**:
  - **Imprima** a sequência de cartas descartadas no formato:  
    `Discarded cards: carta1, carta2, carta3, ...`
  - **Imprima** a carta restante no formato:  
    `Remaining card: carta`

**Exemplo:**

**Entrada:**
```
7
19
10
6
0
```

**Saída:**
```
Discarded cards: 1, 3, 5, 7, 4, 2
Remaining card: 6
Discarded cards: 1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 4, 8, 12, 16, 2, 10, 18, 14
Remaining card: 6
Discarded cards: 1, 3, 5, 7, 9, 2, 6, 10, 8
Remaining card: 4
Discarded cards: 1, 3, 5, 2, 6
Remaining card: 4
```

---

### Explicação do exemplo:

1. Para **n = 7**:
   - Cartas descartadas: `1, 3, 5, 7, 4, 2`.
   - Carta restante: `6`.

2. Para **n = 19**:
   - Cartas descartadas: `1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 4, 8, 12, 16, 2, 10, 18, 14`.
   - Carta restante: `6`.

3. Para **n = 10**:
   - Cartas descartadas: `1, 3, 5, 7, 9, 2, 6, 10, 8`.
   - Carta restante: `4`.

4. Para **n = 6**:
   - Cartas descartadas: `1, 3, 5, 2, 6`.
   - Carta restante: `4`.

programa em C# que implementa a lógica descrita no enunciado:

```csharp
using System;
using System.Collections.Generic;

class URI {

    static void Main(string[] args) { 

        while (true) {
            // Lê o valor de n
            int n = int.Parse(Console.ReadLine());

            // Se n for 0, encerra o programa
            if (n == 0) {
                break;
            }

            // Cria uma fila para simular a pilha de cartas
            Queue<int> cartas = new Queue<int>();

            // Preenche a fila com as cartas de 1 a n
            for (int i = 1; i <= n; i++) {
                cartas.Enqueue(i);
            }

            // Lista para armazenar as cartas descartadas
            List<int> descartadas = new List<int>();

            // Processa as cartas até sobrar apenas uma
            while (cartas.Count > 1) {
                // Descarta a carta do topo
                descartadas.Add(cartas.Dequeue());

                // Move a próxima carta para o final da fila
                cartas.Enqueue(cartas.Dequeue());
            }

            // Imprime as cartas descartadas
            Console.Write("Discarded cards: ");
            for (int i = 0; i < descartadas.Count; i++) {
                Console.Write(descartadas[i]);
                if (i < descartadas.Count - 1) {
                    Console.Write(", ");
                }
            }
            Console.WriteLine();

            // Imprime a carta restante
            Console.WriteLine("Remaining card: " + cartas.Dequeue());
        }
    }
}
```

### Explicação do código:

1. **Leitura de `n`**:
   - O programa lê o valor de `n` (quantidade de cartas).
   - Se `n` for **0**, o programa é encerrado.

2. **Criação da fila de cartas**:
   - Usamos uma `Queue<int>` para simular a pilha de cartas, onde a carta **1** está no topo e a carta **n** na base.

3. **Processamento das cartas**:
   - Enquanto houver mais de uma carta na fila:
     - A carta do topo é descartada e adicionada à lista de cartas descartadas.
     - A próxima carta é movida para o final da fila.

4. **Saída**:
   - As cartas descartadas são impressas no formato:  
     `Discarded cards: carta1, carta2, carta3, ...`
   - A carta restante é impressa no formato:  
     `Remaining card: carta`

### Exemplo de uso:

**Entrada:**
```
7
19
10
6
0
```

**Saída:**
```
Discarded cards: 1, 3, 5, 7, 4, 2
Remaining card: 6
Discarded cards: 1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 4, 8, 12, 16, 2, 10, 18, 14
Remaining card: 6
Discarded cards: 1, 3, 5, 7, 9, 2, 6, 10, 8
Remaining card: 4
Discarded cards: 1, 3, 5, 2, 6
Remaining card: 4
```

### Funcionamento do exemplo:

1. Para **n = 7**:
   - Cartas descartadas: `1, 3, 5, 7, 4, 2`.
   - Carta restante: `6`.

2. Para **n = 19**:
   - Cartas descartadas: `1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 4, 8, 12, 16, 2, 10, 18, 14`.
   - Carta restante: `6`.

3. Para **n = 10**:
   - Cartas descartadas: `1, 3, 5, 7, 9, 2, 6, 10, 8`.
   - Carta restante: `4`.

4. Para **n = 6**:
   - Cartas descartadas: `1, 3, 5, 2, 6`.
   - Carta restante: `4`.

