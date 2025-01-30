Certo dia, os irmãos Little Chitão e Xor Or Oh, exímios digitadores, fizeram um desafio, para ver quem era o melhor na digitação. Para isto, conseguiram um computador que não processa teclas pressionadas continuamente, ou seja, para digitar a mesma letra duas vezes seguidas, precisa pressionar a tecla duas vezes, visto que, pressionar a tecla por mais tempo, não seria considerado toques consecutios. Também mediram o tempo de uma tecla pressionada, que foi de, exatamente, um centésimo de segundo. O desafio seria quem digitasse a palavra “galopeira”, formada por mais letras mas ambos eram muito bons, e chegava num ponto que não era possível contar quantas letras haviam sido digitadas. Então, pediram a sua ajuda para escrever um programa que verifique a palavra digitada e veja quanto tempo foi gasto para a digitação.
Escreva um programa que, dada uma palavra digitada, informe quanto tempo foi gasto para ser digitada.
Entrada
Um número inteiro C será informado, que será a quantidade de casos de teste. Cada caso tem uma palavra, de, no mínimo, 9 e, no máximo 10000 letras.
Saída
Para cada caso de teste, imprima um número T, que é o tempo gasto, em segundos, para digitar a palavra do respectivo caso de teste, com aproximação de duas casas decimais.
Exemplo de Entrada
3
galopeira
galopeeeeeeeeeeeeeeeeeira
galopeeira
Exemplo de Saída
0.09
0.25
0.10

Segue um código didático e detalhado para resolver o problema descrito:

```csharp
using System;

class URI
{
    static void Main(string[] args)
    {
        // Lê o número de casos de teste
        int C = int.Parse(Console.ReadLine());

        for (int i = 0; i < C; i++)
        {
            // Lê a palavra digitada para o caso de teste
            string palavra = Console.ReadLine();

            // Calcula o tempo em segundos: 0.01 segundos por letra
            double tempo = palavra.Length * 0.01;

            // Exibe o resultado formatado com 2 casas decimais
            Console.WriteLine(tempo.ToString("F2"));
        }
    }
}
```

### Explicação do Código:
1. **Entrada do Número de Casos:** 
   - O programa lê a quantidade de casos de teste \( C \).

2. **Iteração Sobre os Casos:** 
   - Para cada caso, lê a palavra digitada.
   - O comprimento da palavra é usado para calcular o tempo gasto (cada letra consome 0.01 segundos).

3. **Cálculo do Tempo:**
   - O tempo é simplesmente \( \text{comprimento da palavra} \times 0.01 \).

4. **Saída Formatada:**
   - O tempo é exibido com duas casas decimais, utilizando `ToString("F2")`.

### Exemplo de Execução:
Entrada:
```
3
galopeira
galopeeeeeeeeeeeeeeeeeira
galopeeira
```

Saída:
```
0.09
0.25
0.10
```

### Observações:
- O programa usa `ToString("F2")` para garantir que a saída seja formatada com exatamente duas casas decimais, como exigido.
- O código é eficiente, mesmo para palavras próximas ao limite máximo de 10.000 letras. 

Se precisar de mais explicações ou ajustes, é só avisar!