

1. **Leia** o número de dias \( N \) que George pode trazer o circo para a cidade.
2. **Leia** o custo diário para manter o circo na cidade.
3. **Leia** a receita prevista para cada um dos \( N \) dias.
4. **Calcule** o lucro máximo que George pode obter ao trazer o circo para a cidade em qualquer sequência de dias (de 0 a \( N \) dias).
5. **Considere** que, se George trouxer o circo por 0 dias, o lucro será $0.
6. **Imprima** o lucro máximo para cada caso de teste.

**Exemplo:**

- **Entrada:**
  ```
  6
  20
  18
  35
  6
  80
  15
  21
  4
  40
  30
  20
  10
  38
  ```

- **Saída:**
  ```
  61
  0
  ```

**Passo a passo:**

1. **Leia** \( N = 6 \) (número de dias).
2. **Leia** o custo diário = $20.
3. **Leia** as receitas diárias: $18, $35, $6, $80, $15, $21.
4. **Calcule** o lucro máximo:
   - Escolha os dias 2, 3 e 4: receita = $35 + $6 + $80 = $121.
   - Custo total = 3 dias * $20 = $60.
   - Lucro = $121 - $60 = $61.
5. **Imprima** o lucro máximo: $61.



```csharp
using System;

class URI {
    static void Main(string[] args) {
        while (true) {
            // Verifica se há mais entradas (EOF)
            string input = Console.ReadLine();
            if (input == null) break;

            // Lê o número de dias (N)
            int N = int.Parse(input);
            

            // Lê o custo diário
            int custoPorDia = int.Parse(Console.ReadLine());
            

            // Lê as receitas diárias
            int[] receitas = new int[N];
            for (int i = 0; i < N; i++) {
                receitas[i] = int.Parse(Console.ReadLine());
                
            }

            // Calcula o lucro máximo
            int lucroMaximo = 0;
            int lucroAtual = 0;

            for (int i = 0; i < N; i++) {
                lucroAtual += receitas[i] - custoPorDia;

                if (lucroAtual < 0) {
                    lucroAtual = 0; // Reinicia o lucro atual se for negativo
                }

                if (lucroAtual > lucroMaximo) {
                    lucroMaximo = lucroAtual; // Atualiza o lucro máximo
                }
            }

            // Imprime o resultado
            Console.WriteLine(lucroMaximo);
        }
    }
}
```

### Explicação do Código:

1. **Leitura da Entrada:**
   - O programa lê o número de dias \( N \), o custo diário e as receitas diárias.

2. **Cálculo do Lucro Máximo:**
   - Usa um algoritmo de subarray contíguo máximo (Kadane's Algorithm) para calcular o lucro máximo.
   - Para cada dia, o lucro atual é atualizado somando a receita do dia e subtraindo o custo diário.
   - Se o lucro atual for negativo, ele é reiniciado para 0.
   - O lucro máximo é atualizado sempre que o lucro atual for maior que o lucro máximo anterior.

3. **Condição de Parada (EOF):**
   - O loop `while (true)` continua até que não haja mais entradas (indicado por `Console.ReadLine()` retornando `null`).

4. **Saída:**
   - Para cada caso de teste, o programa imprime o lucro máximo calculado.

### Exemplo de Entrada e Saída:

**Entrada:**
```
6
20
18
35
6
80
15
21
4
40
30
20
10
38
```

**Saída:**
```
61
0
```

