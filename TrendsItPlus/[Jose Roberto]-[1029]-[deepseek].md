

1. **Receba** o número de casos de teste **N**.
2. **Para cada caso de teste**:
   - **Leia** um inteiro **X** (1 ≤ X ≤ 39).
   - **Calcule** o valor de Fibonacci para **X** usando chamadas recursivas.
   - **Conte** o número de chamadas recursivas feitas durante o cálculo.
3. **Exiba** o resultado no formato:
   ```
   fib(X) = num_calls calls = result
   ```
   Onde:
   - `num_calls` é o número de chamadas recursivas.
   - `result` é o valor de Fibonacci calculado.

**Exemplo de Entrada:**
```
2
5
4
```

**Exemplo de Saída:**
```
fib(5) = 14 calls = 5
fib(4) = 8 calls = 3
```

Agora, aqui está o programa em C# que implementa a lógica solicitada:

```csharp
using System;

class URI {

    static int numCalls;

    static int Fibonacci(int n) {
        numCalls++;
        if (n == 0) return 0;
        if (n == 1) return 1;
        return Fibonacci(n - 1) + Fibonacci(n - 2);
    }

    static void Main(string[] args) { 
        int N = int.Parse(Console.ReadLine());

        for (int i = 0; i < N; i++) {
            int X = int.Parse(Console.ReadLine());
            numCalls = 0;
            int result = Fibonacci(X);
            Console.WriteLine($"fib({X}) = {numCalls - 1} calls = {result}");
        }
    }
}
```

### Explicação do código:
1. **Função `Fibonacci`**:
   - Calcula o valor de Fibonacci para um dado número `n` usando recursão.
   - Incrementa o contador `numCalls` a cada chamada recursiva.

2. **Função `Main`**:
   - Lê o número de casos de teste **N**.
   - Para cada caso de teste:
     - Lê o valor de **X**.
     - Reseta o contador `numCalls`.
     - Calcula o valor de Fibonacci para **X**.
     - Exibe o resultado no formato especificado.

### Exemplo de uso:
Se a entrada for:
```
2
5
4
```

A saída será:
```
fib(5) = 14 calls = 5
fib(4) = 8 calls = 3
```

### Funcionamento:
- Para `fib(5)`, o programa faz 14 chamadas recursivas e calcula o valor 5.
- Para `fib(4)`, o programa faz 8 chamadas recursivas e calcula o valor 3.

