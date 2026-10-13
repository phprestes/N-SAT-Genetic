# N-SAT Genético

Resolução do problema da satisfatibilidade booleana (SAT) com algoritmo genético, para a disciplina **SSC0713 - Sistemas Evolutivos Aplicados à Robótica**.

[Vídeo da apresentação](https://youtu.be/sZxT2KXBwtc)

<p align="center">
  <img alt="Disciplina" src="https://img.shields.io/badge/SSC0713-Sistemas%20Evolutivos%20Aplicados%20%C3%A0%20Rob%C3%B3tica-blue?style=for-the-badge">
  <img alt="Instituição" src="https://img.shields.io/badge/USP-Universidade%20de%20S%C3%A3o%20Paulo-orange?style=for-the-badge">
</p>

> **Disciplina:** SSC0713 - Sistemas Evolutivos Aplicados à Robótica <br>
> **Instituição:** USP - Universidade de São Paulo

<p align="center">
  <img src="https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black" alt="C" />
  <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Tkinter-3776AB?style=for-the-badge" alt="Tkinter" />
  <img src="https://img.shields.io/badge/GNUplot-A42E2B?style=for-the-badge" alt="GNUplot" />
  <img src="https://img.shields.io/badge/Shell-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white" alt="Shell" />
</p>

## Problema da Satisfatibilidade Booleana (SAT)

SAT é um dos problemas fundamentais da teoria da complexidade computacional e o primeiro identificado como NP-completo. Consiste em determinar se existe uma atribuição de valores de verdade às variáveis de uma fórmula booleana que a torne verdadeira. Por exemplo, em $(x_{1}+ \neg x_{3}+x_{4}) \cdot (\neg x_{2}+x_{3}+ \neg x_{4})$, o objetivo é encontrar (ou verificar que não existem) valores para $x_{1}$, $x_{2}$, $x_{3}$, $x_{4}$ que satisfaçam a fórmula. Se existem, a fórmula é satisfatível; caso contrário, insatisfatível.

## Algoritmo Genético

Um Algoritmo Genético (AG) é uma técnica de busca e otimização inspirada na evolução natural (seleção natural, mutação e reprodução), usada em problemas onde a solução exata pode ser inviável, como os NP-completos. Trabalha com uma população de soluções candidatas (indivíduos), geralmente representadas como cromossomos, avaliadas por uma função de fitness.

- **Função de fitness:** no SAT, a quantidade de cláusulas que o cromossomo satisfaz (iguais a 1).
- **Reprodução:** *single point crossover*. Seleciona um ponto aleatório do cromossomo e troca todos os genes subsequentes pelos do melhor indivíduo.
- **Mutação:** quando um novo indivíduo é criado, cada gene tem 5% de chance de ser negado (`x = !x`).

## Requisitos

- **Python 3** com **Tkinter**
- **GNUplot**

## Como Executar

```bash
sudo apt-get install python3-tk gnuplot
python3 interface.py
```

### Como gerar casos de teste

Para gerar casos com N cláusulas e M variáveis, use o script em `CASOS_TESTE`:

```bash
cd CASOS_TESTE
chmod +x geraCasos.sh
./geraCasos.sh
```

Os casos são salvos na pasta `entradas`, dentro de `CASOS_TESTE`.

## Estrutura do Projeto

- `interface.py`: interface gráfica em Tkinter, que executa o solver.
- `sat.c`, `agbinary.c`, `agbinary.h`, `parameters.h`: algoritmo genético para SAT, em C.
- `CASOS_TESTE/`: gerador de casos (`generator.c`, `geraCasos.sh`) e entradas de exemplo.
- `2SAT_KOSARAJU/`: solução de 2-SAT com o algoritmo de Kosaraju, em C++, com casos de teste.

## Autores

- Dante Brito Lourenço
- João Gabriel Pieroli da Silva
- Juan Marque Jordão
- Pedro Henrique de Sousa Prestes
- Pedro Lunkes Villela
