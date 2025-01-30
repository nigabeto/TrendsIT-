Você está ajudando a desenvolver um sistema de gerenciamento de weblog chamado bloggo. Embora bloggo coloque todo o conteúdo direto no website em HTML, nem todos autores apreciam usar tags HTML em seus textos. Para tornar a vida deles mais fáceis, bloggo oferece uma sintaxe simples chamada atalhos para obter alguns efeitos textuais em HTML. Sua tarefa é, dado um documento escrito com atalhos, traduzi-lo para o HTML apropriado.

Um atalho é usado para colocar texto em itálico. HTML faz isto com as tags <i> e </i>, mas no bloggo um autor pode simplesmente colocar um pedaço de texto entre dois caracteres de sublinhado, '_'. Portanto, onde um autor escreve
  You _should_ see the baby elephant at the zoo!
                
bloggo vai publicar o seguinte:
  You <i>should</i> see the baby elephant at the zoo!
                
Outro atalho serve para colocar texto em negrito, o que, em HTML, é feito com as tags <b> e </b>. Bloggo permite aos autores fazer o mesmo com pares do caractere asterisco, '*'. Quando um autor escreve o texto
  Move it from *Receiving* to *Accounts Payable*.
                
ele vai sair no website assim:
  Move it from <b>Receiving</b> to <b>Accounts Payable</b>.
                
Entrada
A entrada contem vários casos de teste. Cada caso de teste é composto por uma linha que contem uma string texto, com zero ou mais usos dos atalhos itálico e negrito. Cada texto tem de 1 a 50 caracteres, inclusive. Os únicos caracteres permitidos no texto são os caracteres alfabéticos (de 'a' a 'z' e de 'A' a 'Z'), o sublinhado ('_'), o asterisco ('*'), o caractere de espaço e os símbolos de pontuação ',', ';', '.', '!', '?', '-', '(' e ')'. O caractere sublinhado '_' ocorre no texto um número par de vezes. O asterisco '*' também aparece um número par de vezes no texto. Nenhuma substring do texto entre um par de sublinhados ou entre um par de asteriscos pode conter outros sublinhados ou asteriscos, respectivamente.
Saída
Para cada linha de entrada seu programa deve gerar uma linha de saída com o texto traduzido para HTML como demonstrado nos exemplos abaixo. Para tornar itálico um pedaço de texto no HTML, você deve iniciar este pedaço com a tag <i> e terminá-lo com a tag </i>. Para texto em negrito, inicie com <b> e termine com </b>.

O final da entrada é determinado por EOF.

Exemplo de Entrada
You _should_ see the new walrus at the zoo!
Move it from *Accounts Payable* to *Receiving*.
I saw _Chelydra serpentina_ in *Centennial Park*.
_ _ __ _ yabba dabba _ * dooooo * ****
_now_I_know_*my*_ABC_next_time_*sing*it_with_me

Exemplo de Saída
You <i>should</i> see the new walrus at the zoo!
Move it from <b>Accounts Payable</b> to <b>Receiving</b>.
I saw <i>Chelydra serpentina</i> in <b>Centennial Park</b>.
<i> </i> <i></i> <i> yabba dabba </i> <b> dooooo </b> <b></b><b></b>
<i>now</i>I<i>know</i><b>my</b><i>ABC</i>next<i>time</i><b>sing</b>it<i>with</i>me

Segue a solução completa em C# para o problema proposto:

```csharp
using System;

class URI
{
    static void Main(string[] args)
    {
        string linha;
        while ((linha = Console.ReadLine()) != null)
        {
            bool italico = false;
            bool negrito = false;

            // Processa cada caractere da linha
            for (int i = 0; i < linha.Length; i++)
            {
                char c = linha[i];

                if (c == '_')
                {
                    // Alterna entre abrir e fechar a tag <i>
                    if (italico)
                        Console.Write("</i>");
                    else
                        Console.Write("<i>");
                    italico = !italico;
                }
                else if (c == '*')
                {
                    // Alterna entre abrir e fechar a tag <b>
                    if (negrito)
                        Console.Write("</b>");
                    else
                        Console.Write("<b>");
                    negrito = !negrito;
                }
                else
                {
                    // Apenas escreve o caractere
                    Console.Write(c);
                }
            }

            // Imprime nova linha ao final de cada caso de teste
            Console.WriteLine();
        }
    }
}
```

### Explicação do Código:

1. **Leitura do Input:**
   - O programa lê as linhas de entrada até o final do arquivo (EOF). O método `Console.ReadLine()` retorna `null` quando não há mais linhas.

2. **Alternância de Tags:**
   - Usa-se duas variáveis booleanas (`italico` e `negrito`) para rastrear se uma tag `<i>` ou `<b>` está aberta.
   - Quando um caractere `_` ou `*` é encontrado, ele alterna entre abrir ou fechar a tag correspondente.

3. **Processamento Caracter por Caracter:**
   - Caso o caractere seja `_`, é substituído por `<i>` ou `</i>`.
   - Caso o caractere seja `*`, é substituído por `<b>` ou `</b>`.
   - Outros caracteres são exibidos como estão.

4. **Saída:**
   - Após processar cada linha, o programa imprime o texto formatado em HTML.

### Exemplo de Execução:

#### Entrada:
```
You _should_ see the new walrus at the zoo!
Move it from *Accounts Payable* to *Receiving*.
I saw _Chelydra serpentina_ in *Centennial Park*.
_ _ __ _ yabba dabba _ * dooooo * ****
_now_I_know_*my*_ABC_next_time_*sing*it_with_me
```

#### Saída:
```
You <i>should</i> see the new walrus at the zoo!
Move it from <b>Accounts Payable</b> to <b>Receiving</b>.
I saw <i>Chelydra serpentina</i> in <b>Centennial Park</b>.
<i> </i> <i></i> <i> yabba dabba </i> <b> dooooo </b> <b></b><b></b>
<i>now</i>I<i>know</i><b>my</b><i>ABC</i>next<i>time</i><b>sing</b>it<i>with</i>me
```

### Observações:
- A solução lida eficientemente com a alternância de tags para itálico e negrito.
- O uso de variáveis booleanas simplifica a lógica de alternância.
- O código atende ao limite de 50 caracteres por linha de texto. 

Se precisar de mais explicações ou adaptações, estou à disposição!