Desenvolva um programa em C# com as seguintes orientaçoes:

Leia um número inteiro N, que indica quantos números você vai receber.

Leia os N números fornecidos.

Conte quantas vezes cada número aparece.

Ordene os números distintos em ordem crescente.

Imprima cada número e a quantidade de vezes que ele aparece, seguindo a ordem crescente.

Detalhes adicionais:

O valor de N é um número inteiro.

Cada número lido (X) estará no intervalo 1 ≤ X ≤ 2000.

Nenhum número aparecerá mais do que 20 vezes na entrada. 


Aqui está a implementação em C# seguindo as orientações:

Esse programa lê um número inteiro \( N \), recebe \( N \) números, conta as ocorrências de cada um, ordena-os em ordem crescente e imprime o resultado no formato especificado.

No codigo realizado, as condiçoes de testes para que "Cada número lido (X) estará no intervalo 1 ≤ X ≤ 2000." e "Nenhum número aparecerá mais do que 20 vezes na entrada" parecem não terem sido atendidas, pois testei a inserção de numero maior que 2000 e inserção do mesmo numero mais de 20 vezes e não houve restrição. Pode verificar?

Adicionei verificações para garantir que os números estejam dentro do intervalo permitido (1 ≤ X ≤ 2000) e que nenhum número seja inserido mais de 20 vezes. Caso contrário, uma mensagem será exibida informando que a entrada foi ignorada. Teste novamente e veja se atende às suas expectativas!

using System;
using System.Collections.Generic;
using System.Linq;

class URI
{
    static void Main(string[] args)
    {
        // Lê o número de entradas
        int N = int.Parse(Console.ReadLine());
        
        Dictionary<int, int> contagem = new Dictionary<int, int>();
        
        // Lê os números e conta suas ocorrências
        for (int i = 0; i < N; i++)
        {
            int numero = int.Parse(Console.ReadLine());
            
            // Verifica se o número está no intervalo permitido
            if (numero < 1 || numero > 2000)
            {
                Console.WriteLine("Número fora do intervalo permitido (1 ≤ X ≤ 2000). Ignorado.");
                continue;
            }
            
            if (contagem.ContainsKey(numero))
            {
                if (contagem[numero] >= 20)
                {
                    Console.WriteLine($"Número {numero} já inserido 20 vezes. Ignorado.");
                    continue;
                }
                contagem[numero]++;
            }
            else
            {
                contagem[numero] = 1;
            }
        }
        
        // Ordena os números distintos em ordem crescente
        foreach (var item in contagem.OrderBy(x => x.Key))
        {
            Console.WriteLine($"{item.Key} aparece {item.Value} vez(es)");
        }
    }
}
