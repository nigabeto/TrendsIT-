Segue o código mais didático e detalhado para o problema descrito: 

```csharp
using System;

class URI {

    static void Main(string[] args) {
        while (true) {
            // Lê o valor de N
            Console.Write("Digite o valor de N (0 para sair): ");
            int N = int.Parse(Console.ReadLine());

            // Verifica se o valor é zero, o que encerra o programa
            if (N == 0) {
                break;
            }

            // Verifica se o valor de N está no intervalo permitido (0 ≤ N ≤ 100)
            if (N < 0 || N > 100) {
                Console.WriteLine("Por favor, digite um valor entre 0 e 100.");
                continue;
            }

            // Cria e preenche a matriz M de tamanho NxN
            int[,] matriz = new int[N, N];
            for (int i = 0; i < N; i++) {
                for (int j = 0; j < N; j++) {
                    // Define o valor da célula com base na menor distância até a borda
                    matriz[i, j] = Math.Abs(i - j) + 1;
                }
            }

            // Imprime a matriz no formato especificado
            for (int i = 0; i < N; i++) {
                for (int j = 0; j < N; j++) {
                    // Formata cada número com largura fixa de 3 caracteres
                    Console.Write(matriz[i, j].ToString().PadLeft(3));

                    // Adiciona espaço entre números, exceto no final da linha
                    if (j < N - 1) {
                        Console.Write(" ");
                    }
                }
                Console.WriteLine(); // Finaliza a linha
            }

            Console.WriteLine(); // Linha em branco após cada matriz
        }
    }
}
```

### Explicação do Código:
1. **Leitura do valor de \( N \):** O programa continua pedindo valores até que seja inserido \( N = 0 \), o que termina a execução.
2. **Validação de \( N \):** Verifica se \( N \) está dentro do intervalo permitido \( (0 \leq N \leq 100) \).
3. **Preenchimento da Matriz:**
   - Cada valor na posição \( (i, j) \) é calculado como \( |i - j| + 1 \), garantindo a construção da matriz conforme o exemplo.
4. **Impressão:**
   - Cada número é formatado com 3 espaços, justificado à direita.
   - Linhas são separadas adequadamente e não há espaços extras ao final das linhas.
   - Uma linha em branco é adicionada após cada matriz.

Se precisar de mais detalhes ou ajustes, é só avisar!