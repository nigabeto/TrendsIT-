Complete o código abaixo, de tal forma que sejam criadas as variáveis correspondentes a 
Hora inicial, MinutoInicial, HoraFinal e MinutoFinal de um jogo e 
leia Hora inicial, MinutoInicial, HoraFinal e MinutoFinal. A seguir calcule a duração do jogo.
Obs: O jogo tem duração mínima de um (1) minuto e duração máxima de 24 horas.
Entrada
Quatro números inteiros representando a hora de início e fim do jogo.
Saída
imprima a seguinte mensagem: “O JOGO DUROU XXX HORA(S) E YYY MINUTO(S)”  com comando de final de linha no final da resposta.
using System; 

class URI {

    static void Main(string[] args) { 

        /**
         * Escreva a sua solução aqui
         */

    }

}

Aqui está o código completo para resolver o problema descrito. O código lê a hora inicial, minuto inicial, hora final e minuto final de um jogo, calcula a duração do jogo e imprime a mensagem com a duração em horas e minutos.

```csharp
using System;

class URI {

    static void Main(string[] args) { 

        // Lê os valores de entrada
        string[] entrada = Console.ReadLine().Split(' ');
        int horaInicial = int.Parse(entrada[0]);
        int minutoInicial = int.Parse(entrada[1]);
        int horaFinal = int.Parse(entrada[2]);
        int minutoFinal = int.Parse(entrada[3]);

        // Converte o tempo inicial e final para minutos
        int inicioEmMinutos = horaInicial * 60 + minutoInicial;
        int fimEmMinutos = horaFinal * 60 + minutoFinal;

        // Calcula a duração em minutos
        int duracaoEmMinutos;
        if (fimEmMinutos > inicioEmMinutos) {
            duracaoEmMinutos = fimEmMinutos - inicioEmMinutos;
        } else {
            duracaoEmMinutos = (24 * 60) - (inicioEmMinutos - fimEmMinutos);
        }

        // Converte a duração de volta para horas e minutos
        int duracaoHoras = duracaoEmMinutos / 60;
        int duracaoMinutos = duracaoEmMinutos % 60;

        // Imprime a duração do jogo
        Console.WriteLine($"O JOGO DUROU {duracaoHoras} HORA(S) E {duracaoMinutos} MINUTO(S)");
    }
}
```

### Explicação do Código:

1. **Leitura dos Dados:**
   - O código lê a entrada do usuário, que consiste em quatro números inteiros representando a hora inicial, minuto inicial, hora final e minuto final.
   - Esses valores são armazenados nas variáveis `horaInicial`, `minutoInicial`, `horaFinal` e `minutoFinal`.

2. **Conversão para Minutos:**
   - O tempo inicial e final são convertidos para minutos totais desde o início do dia (00:00) para facilitar o cálculo da duração.
   - `inicioEmMinutos` e `fimEmMinutos` armazenam esses valores.

3. **Cálculo da Duração:**
   - Se o tempo final for maior que o tempo inicial, a duração é simplesmente a diferença entre os dois.
   - Caso contrário, o jogo terminou no dia seguinte, então a duração é calculada como a diferença entre o tempo final e o tempo inicial, somando 24 horas (1440 minutos).

4. **Conversão de Volta para Horas e Minutos:**
   - A duração total em minutos é convertida de volta para horas e minutos.

5. **Impressão do Resultado:**
   - A duração do jogo é impressa no formato especificado.

### Exemplo de Entrada e Saída:

**Entrada:**
```
7 8 9 10
```

**Saída:**
```
O JOGO DUROU 2 HORA(S) E 2 MINUTO(S)
```

**Entrada:**
```
23 59 0 1
```

**Saída:**
```
O JOGO DUROU 0 HORA(S) E 2 MINUTO(S)
```

Este código garante que a duração do jogo seja calculada corretamente, mesmo que o jogo termine no dia seguinte ao início.