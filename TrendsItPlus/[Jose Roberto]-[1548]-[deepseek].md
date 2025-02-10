
1. **Receba** o número de casos de teste **N**.
2. **Para cada caso de teste**:
   - **Leia** o número de alunos **M** (1 ≤ M ≤ 1000).
   - **Leia** as notas dos alunos **Pi** (1 ≤ Pi ≤ 1000), em ordem de chegada.
3. **Reordene** a fila dos alunos de acordo com as notas em matemática, da maior para a menor.
4. **Conte** quantos alunos **não precisaram trocar de lugar** após a reordenação.
5. **Exiba** o número de alunos que permaneceram na mesma posição.

**Exemplo de Entrada:**
```
3
3
100 80 90
4
100 120 30 50
4
100 90 30 25
```

**Exemplo de Saída:**
```
1
0
4
```

### Passo a passo:
1. **Para cada caso de teste**:
   - **Armazene** as notas dos alunos e suas posições originais.
   - **Ordene** as notas em ordem decrescente.
   - **Compare** a posição original de cada aluno com sua nova posição após a ordenação.
   - **Conte** quantos alunos permaneceram na mesma posição.
2. **Exiba** o resultado para cada caso de teste.

### Explicação do exemplo:
- No primeiro caso de teste (`100 80 90`), após a ordenação, a fila fica `100 90 80`. Apenas o aluno com nota **100** permaneceu na mesma posição. Saída: `1`.
- No segundo caso de teste (`100 120 30 50`), após a ordenação, a fila fica `120 100 50 30`. Nenhum aluno permaneceu na mesma posição. Saída: `0`.
- No terceiro caso de teste (`100 90 30 25`), após a ordenação, a fila fica `100 90 30 25`. Todos os alunos permaneceram na mesma posição. Saída: `4`.



```csharp
using System;
using System.Linq;

class URI {

    static void Main(string[] args) { 
        // Lê o número de casos de teste
        int N = int.Parse(Console.ReadLine());

        // Processa cada caso de teste
        for (int i = 0; i < N; i++) {
            // Lê o número de alunos
            int M = int.Parse(Console.ReadLine());

            // Verifica se M está dentro do intervalo válido
            if (M < 1 || M > 1000) {
                Console.WriteLine("M deve estar no intervalo 1 ≤ M ≤ 1000.");
                return;
            }

            // Lê as notas dos alunos
            int[] notas = Console.ReadLine().Split(' ').Select(int.Parse).ToArray();

            // Verifica se todas as notas estão dentro do intervalo válido
            if (notas.Any(p => p < 1 || p > 1000)) {
                Console.WriteLine("As notas devem estar no intervalo 1 ≤ Pi ≤ 1000.");
                return;
            }

            // Armazena as notas com suas posições originais
            var alunos = notas.Select((nota, indice) => new { Nota = nota, PosicaoOriginal = indice }).ToArray();

            // Ordena os alunos por nota em ordem decrescente
            var alunosOrdenados = alunos.OrderByDescending(a => a.Nota).ToArray();

            // Conta quantos alunos permaneceram na mesma posição
            int contador = 0;
            for (int j = 0; j < M; j++) {
                if (alunosOrdenados[j].PosicaoOriginal == j) {
                    contador++;
                }
            }

            // Exibe o resultado
            Console.WriteLine(contador);
        }
    }
}
```

### Explicação do código:
1. **Leitura de N**:
   - O número de casos de teste **N** é lido.

2. **Processamento de cada caso de teste**:
   - Para cada caso de teste, o número de alunos **M** é lido e validado (1 ≤ M ≤ 1000).
   - As notas dos alunos são lidas e validadas (1 ≤ Pi ≤ 1000).

3. **Armazenamento das notas com posições originais**:
   - Cada nota é armazenada junto com sua posição original na fila.

4. **Ordenação**:
   - Os alunos são ordenados por nota em ordem decrescente.

5. **Contagem de alunos que não mudaram de posição**:
   - Compara-se a posição original de cada aluno com sua nova posição após a ordenação.
   - Conta-se quantos alunos permaneceram na mesma posição.

6. **Exibição do resultado**:
   - O número de alunos que não mudaram de posição é exibido para cada caso de teste.

### Exemplo de uso:
Se a entrada for:
```
3
3
100 80 90
4
100 120 30 50
4
100 90 30 25
```

A saída será:
```
1
0
4
```

### Funcionamento:
- No primeiro caso de teste (`100 80 90`), após a ordenação, a fila fica `100 90 80`. Apenas o aluno com nota **100** permaneceu na mesma posição. Saída: `1`.
- No segundo caso de teste (`100 120 30 50`), após a ordenação, a fila fica `120 100 50 30`. Nenhum aluno permaneceu na mesma posição. Saída: `0`.
- No terceiro caso de teste (`100 90 30 25`), após a ordenação, a fila fica `100 90 30 25`. Todos os alunos permaneceram na mesma posição. Saída: `4`.

