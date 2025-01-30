Aqui está a implementação em C# para resolver o problema descrito:

```csharp
using System;

class URI {

    static void Main(string[] args) {
        while (true) {
            // Lê a ordem da matriz
            int N = int.Parse(Console.ReadLine());
            if (N == 0) break; // Condição de parada

            int[,] matriz = new int[N, N];

            // Construção da matriz
            for (int i = 0; i < N; i++) {
                for (int j = 0; j < N; j++) {
                    matriz[i, j] = Math.Min(Math.Min(i, j), Math.Min(N - i - 1, N - j - 1)) + 1;
                }
            }

            // Impressão da matriz
            for (int i = 0; i < N; i++) {
                for (int j = 0; j < N; j++) {
                    Console.Write($"{matriz[i, j],3}"); // Formata os números à direita
                    if (j < N - 1) Console.Write(" "); // Adiciona espaço entre os números
                }
                Console.WriteLine();
            }
            Console.WriteLine(); // Linha em branco após cada matriz
        }
    }
}
```

### Explicação do código:
1. **Entrada e parada do loop**: 
   - O programa lê valores de entrada continuamente até que `0` seja informado, momento em que ele para.

2. **Construção da matriz**:
   - A matriz é preenchida de acordo com as menores distâncias até as bordas (esquerda, direita, superior, inferior).

3. **Formatação da saída**:
   - Cada número é formatado para ocupar 3 espaços, justificado à direita.
   - Não há espaços no final das linhas da matriz.
   - Após cada matriz, há uma linha em branco.

### Exemplo de Entrada:
```
1
2
3
4
0
```

### Exemplo de Saída:
```
  1

  1   1
  1   1

  1   1   1
  1   2   1
  1   1   1

  1   1   1   1
  1   2   2   1
  1   2   2   1
  1   1   1   1
```

Pronto! Este código atende todos os requisitos apresentados.