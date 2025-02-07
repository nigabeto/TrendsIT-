
---

**Instruções:**

1. **Leia** um número inteiro **N**, que representa a quantidade de casos de teste.
2. Para cada caso de teste:
   - **Leia** uma string que pode conter os caracteres `<`, `>` e `.`.
   - **Remova** todas as partículas de areia `.` da string.
   - **Conte** quantos diamantes `<>` podem ser formados.
     - Cada vez que um diamante é formado, **remova** esses caracteres da string.
     - **Repita** o processo até que não seja possível formar mais diamantes.
3. **Imprima** a quantidade de diamantes extraídos para cada caso de teste.

**Entrada:**
- A primeira linha contém um número inteiro **N**, indicando a quantidade de casos de teste.
- As próximas **N** linhas contêm strings com até 1000 caracteres, incluindo `<`, `>` e `.`.

**Saída:**
- Para cada caso de teste, **imprima** a quantidade de diamantes `<>` que podem ser extraídos.

**Exemplo:**

**Entrada:**
```
2
<..><.<..>>
<<<..<......<<<<....>
```

**Saída:**
```
3
1
```

---

### Explicação do exemplo:

1. No primeiro caso de teste (`<..><.<..>>`):
   - Após remover as partículas de areia `.`, a string se torna `<<><<>>`.
   - São formados 3 diamantes: `<>`, `<>` e `<>`.

2. No segundo caso de teste (`<<<..<......<<<<....>`):
   - Após remover as partículas de areia `.`, a string se torna `<<<<<<<<`.
   - Apenas 1 diamante pode ser formado: `<>`.

Aqui está o programa em C# que resolve o problema descrito, seguindo o exemplo de entrada e saída fornecido:

```csharp
using System;
using System.Collections.Generic;

class URI {

    static void Main(string[] args) { 

        // Lê o número de casos de teste
        int N = int.Parse(Console.ReadLine());

        for (int i = 0; i < N; i++) {
            // Lê a string de entrada
            string entrada = Console.ReadLine();

            // Remove todas as partículas de areia '.' da string
            string filtrada = entrada.Replace(".", "");

            // Usa uma pilha para contar os diamantes
            Stack<char> pilha = new Stack<char>();
            int diamantes = 0;

            // Percorre a string filtrada
            foreach (char c in filtrada) {
                if (c == '<') {
                    // Empilha '<'
                    pilha.Push(c);
                }
                else if (c == '>') {
                    // Se encontrar '>' e houver '<' na pilha, forma um diamante
                    if (pilha.Count > 0 && pilha.Peek() == '<') {
                        pilha.Pop(); // Remove o '<' da pilha
                        diamantes++; // Incrementa a contagem de diamantes
                    }
                }
            }

            // Imprime a quantidade de diamantes para o caso de teste atual
            Console.WriteLine(diamantes);
        }
    }
}
```

### Explicação do código:

1. **Leitura da entrada**:
   - O programa começa lendo o número de casos de teste (`N`).
   - Para cada caso de teste, lê a string de entrada.

2. **Filtragem da string**:
   - Remove todas as partículas de areia `.` da string usando o método `Replace`.

3. **Contagem de diamantes**:
   - Usa uma pilha (`Stack<char>`) para rastrear os caracteres `<`.
   - Percorre a string filtrada:
     - Se encontrar `<`, empilha-o.
     - Se encontrar `>` e houver um `<` no topo da pilha, forma um diamante e incrementa a contagem.

4. **Saída**:
   - Para cada caso de teste, imprime a quantidade de diamantes encontrados.

### Exemplo de uso:

**Entrada:**
```
2
<..><.<..>>
<<<..<......<<<<....>
```

**Saída:**
```
3
1
```

### Funcionamento do exemplo:

1. **Primeiro caso de teste (`<..><.<..>>`)**:
   - Após remover as partículas de areia, a string se torna `<<><<>>`.
   - São formados 3 diamantes: `<>`, `<>` e `<>`.

2. **Segundo caso de teste (`<<<..<......<<<<....>`)**:
   - Após remover as partículas de areia, a string se torna `<<<<<<<<`.
   - Apenas 1 diamante pode ser formado: `<>`.

