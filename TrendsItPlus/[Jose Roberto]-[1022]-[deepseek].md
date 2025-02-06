
---

**Instruções:**

1. **Leia** uma expressão matemática composta por dois números racionais (no formato `numerador / denominador`) e um operador.
2. **Separe** cada operando e operador por um espaço em branco.
3. **Calcule** o resultado da operação seguindo estas regras:
   - **Soma**: \((N1 \times D2 + N2 \times D1) / (D1 \times D2)\)
   - **Subtração**: \((N1 \times D2 - N2 \times D1) / (D1 \times D2)\)
   - **Multiplicação**: \((N1 \times N2) / (D1 \times D2)\)
   - **Divisão**: \((N1 \times D2) / (N2 \times D1)\)
4. **Simplifique** o resultado, se possível.
5. **Apresente** o resultado no formato: `resultado = resultado simplificado`.
   - Se não for possível simplificar, repita o mesmo valor após o sinal de igualdade.

**Entrada:**
- A primeira linha contém um número inteiro **N**, que indica a quantidade de casos de teste.
- Para cada caso de teste, **leia**:
  - Um número racional **X** (no formato `numerador / denominador`).
  - Um operador (`+`, `-`, `*` ou `/`).
  - Outro número racional **Y** (no formato `numerador / denominador`).

**Saída:**
- Para cada caso de teste, **imprima** o resultado da operação no formato `resultado = resultado simplificado`.

**Exemplo:**

**Entrada:**
```
1 / 2 + 3 / 4
2 / 3 * 4 / 5
```

**Saída:**
```
10/8 = 5/4
8/15 = 8/15
```

---

using System;

class URI {

    // Função para calcular o máximo divisor comum (MDC)
    static int MDC(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }

    // Função para simplificar uma fração
    static string Simplificar(int numerador, int denominador) {
        int mdc = MDC(Math.Abs(numerador), Math.Abs(denominador));
        int simplificadoNum = numerador / mdc;
        int simplificadoDen = denominador / mdc;

        // Garantir que o denominador seja positivo
        if (simplificadoDen < 0) {
            simplificadoNum *= -1;
            simplificadoDen *= -1;
        }

        return $"{simplificadoNum}/{simplificadoDen}";
    }

    static void Main(string[] args) { 

        // Lê o número de casos de teste
        int N = int.Parse(Console.ReadLine());

        for (int i = 0; i < N; i++) {
            // Lê a expressão
            string[] expressao = Console.ReadLine().Split(' ');

            // Extrai os valores
            int N1 = int.Parse(expressao[0]);
            int D1 = int.Parse(expressao[2]);
            char operador = char.Parse(expressao[3]);
            int N2 = int.Parse(expressao[4]);
            int D2 = int.Parse(expressao[6]);

            int numeradorResultado = 0;
            int denominadorResultado = 0;

            // Realiza a operação conforme o operador
            switch (operador) {
                case '+':
                    numeradorResultado = N1 * D2 + N2 * D1;
                    denominadorResultado = D1 * D2;
                    break;
                case '-':
                    numeradorResultado = N1 * D2 - N2 * D1;
                    denominadorResultado = D1 * D2;
                    break;
                case '*':
                    numeradorResultado = N1 * N2;
                    denominadorResultado = D1 * D2;
                    break;
                case '/':
                    numeradorResultado = N1 * D2;
                    denominadorResultado = N2 * D1;
                    break;
                default:
                    throw new ArgumentException("Operador inválido.");
            }

            // Simplifica o resultado
            string resultadoSimplificado = Simplificar(numeradorResultado, denominadorResultado);

            // Exibe o resultado no formato solicitado
            Console.WriteLine($"{numeradorResultado}/{denominadorResultado} = {resultadoSimplificado}");
        }
    }
}

Aqui está o programa em C# que resolve o problema descrito, seguindo o exemplo de entrada e saída fornecido:

```csharp
using System;

class URI {

    // Função para calcular o máximo divisor comum (MDC)
    static int MDC(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }

    // Função para simplificar uma fração
    static string Simplificar(int numerador, int denominador) {
        int mdc = MDC(Math.Abs(numerador), Math.Abs(denominador));
        int simplificadoNum = numerador / mdc;
        int simplificadoDen = denominador / mdc;

        // Garantir que o denominador seja positivo
        if (simplificadoDen < 0) {
            simplificadoNum *= -1;
            simplificadoDen *= -1;
        }

        return $"{simplificadoNum}/{simplificadoDen}";
    }

    static void Main(string[] args) { 

        // Lê o número de casos de teste
        int N = int.Parse(Console.ReadLine());

        for (int i = 0; i < N; i++) {
            // Lê a expressão
            string[] expressao = Console.ReadLine().Split(' ');

            // Extrai os valores
            int N1 = int.Parse(expressao[0]);
            int D1 = int.Parse(expressao[2]);
            char operador = char.Parse(expressao[3]);
            int N2 = int.Parse(expressao[4]);
            int D2 = int.Parse(expressao[6]);

            int numeradorResultado = 0;
            int denominadorResultado = 0;

            // Realiza a operação conforme o operador
            switch (operador) {
                case '+':
                    numeradorResultado = N1 * D2 + N2 * D1;
                    denominadorResultado = D1 * D2;
                    break;
                case '-':
                    numeradorResultado = N1 * D2 - N2 * D1;
                    denominadorResultado = D1 * D2;
                    break;
                case '*':
                    numeradorResultado = N1 * N2;
                    denominadorResultado = D1 * D2;
                    break;
                case '/':
                    numeradorResultado = N1 * D2;
                    denominadorResultado = N2 * D1;
                    break;
                default:
                    throw new ArgumentException("Operador inválido.");
            }

            // Simplifica o resultado
            string resultadoSimplificado = Simplificar(numeradorResultado, denominadorResultado);

            // Exibe o resultado no formato solicitado
            Console.WriteLine($"{numeradorResultado}/{denominadorResultado} = {resultadoSimplificado}");
        }
    }
}
```

### Explicação do código:

1. **Função MDC**:
   - Calcula o máximo divisor comum (MDC) usando o algoritmo de Euclides. Isso é necessário para simplificar as frações.

2. **Função Simplificar**:
   - Recebe um numerador e um denominador e retorna a fração simplificada, garantindo que o denominador seja positivo.

3. **Leitura da entrada**:
   - O programa lê o número de casos de teste (`N`).
   - Para cada caso de teste, lê a expressão e extrai os valores dos numeradores, denominadores e o operador.

4. **Cálculo do resultado**:
   - Dependendo do operador (`+`, `-`, `*`, `/`), o programa calcula o numerador e o denominador do resultado.

5. **Simplificação e saída**:
   - O resultado é simplificado usando a função `Simplificar`.
   - O programa imprime o resultado no formato `resultado = resultado simplificado`.

### Exemplo de uso:

**Entrada:**
```
4
1 / 2 + 3 / 4
1 / 2 - 3 / 4
2 / 3 * 6 / 6
1 / 2 / 3 / 4
```

**Saída:**
```
10/8 = 5/4
-2/8 = -1/4
12/18 = 2/3
4/6 = 2/3
```

