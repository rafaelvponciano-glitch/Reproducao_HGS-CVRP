# Reproducao do HGS-CVRP
## Artigo: Hybrid Genetic Search for the CVRP: Open-source implementation and SWAP* neighborhood

Este repositorio apresenta uma tentativa de reproducao dos resultados do artigo:

Vidal (2022) – Hybrid Genetic Search for the CVRP: Open-source implementation and SWAP* neighborhood.

Link do artigo: https://www.sciencedirect.com/science/article/pii/S030505482100349X

O objetivo e comparar o desempenho da implementacao publica disponibilizada no GitHub com os numeros apresentados no trabalho original.

Equioe
Rafael Ponciano Vasceoncelos da Silva
Marco Antônio Oliveira Machado
Igor Rafael Carvalho Gonçalves

## Referencias

[1] Vidal, T.; Crainic, T.G.; Gendreau, M.; Lahrichi, N.; Rei, W. (2012).  
A hybrid genetic algorithm for multidepot and periodic VRPs.  
Operations Research, 60(3), 611–624.

[2] Vidal, T. (2022).  
Hybrid Genetic Search for the CVRP: open-source implementation and SWAP* neighborhood.  
Computers & Operations Research, 140, 105643.


## Resultados e Comparação

O artigo demonstra que o metodo HGS + SWAP*:

- encontra solucoes de menor custo para o CVRP;
- realiza mais melhoras locais devido a vizinhanca SWAP*;
- apresenta bom custo-beneficio mesmo com custo computacional maior;
- se destaca em instancias grandes, rotas longas e movimentos entre rotas.

---

## Metodologia de Reprodução

Repositorio oficial utilizado, onde estão os arquivos:
https://github.com/vidalt/HGS-CVRP

Condicoes adotadas nesta reproducao:

- Ambiente Linux  
- 10 seeds por instancia  
- Tempo de execucao: 30 segundos por instancia (-t 30)  
- Avaliacao baseada em Avg, Best, Gap e Gap Medio  
- Comparacao com as tabelas apresentadas no artigo

---

## Compilacao

E necessario possuir CMake e um compilador C++.

```bash
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release -G "Unix Makefiles"
make bin

```
Isso irá gerar o arquivo executável hgsno builddiretório.
Após compilar o executável, experimente um exemplo:
```bash
./hgs ../Instances/CVRP/X-n157-k13.vrp mySolution.sol -seed 1 -t 30
```

