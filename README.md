# Reproducao do HGS-CVRP
## Hybrid Genetic Search for the CVRP: Open-source implementation and SWAP* neighborhood

Este repositorio apresenta uma tentativa de reproducao dos resultados do artigo:

Vidal (2022) – Hybrid Genetic Search for the CVRP: Open-source implementation and SWAP* neighborhood.

O objetivo e comparar o desempenho da implementacao publica disponibilizada no GitHub com os numeros apresentados no trabalho original.

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

Repositorio oficial utilizado:
https://github.com/vidalt/HGS-CVRP

Condicoes adotadas nesta reproducao:

- Ambiente Linux  
- 10 seeds por instancia  
- Tempo de execucao: 30 segundos por instancia (-t 30)  
- Avaliacao baseada em Avg, Best, Gap e Gap Medio  
- Comparacao com as tabelas apresentadas no artigo

Observacao: o codigo publico nao e identico ao utilizado no paper. Diferencas nos resultados sao esperadas.

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

Licença MIT

Direitos autorais (c) 2020 Thibaut Vidal

Fica concedida permissão, gratuitamente, a qualquer pessoa que obtenha uma cópia.
deste software e arquivos de documentação associados (o "Software"), para lidar com
no Software sem restrições, incluindo, sem limitação, os direitos
usar, copiar, modificar, mesclar, publicar, distribuir, sublicenciar e/ou vender
cópias do Software e permitir que as pessoas a quem o Software é
fornecido para tal, sujeito às seguintes condições:

O aviso de direitos autorais acima e este aviso de permissão devem ser incluídos em todos os documentos.
cópias ou partes substanciais do Software.

O SOFTWARE É FORNECIDO "NO ESTADO EM QUE SE ENCONTRA", SEM GARANTIA DE QUALQUER TIPO, EXPRESSA OU IMPLÍCITA.
IMPLÍCITAS, INCLUINDO, MAS NÃO SE LIMITANDO ÀS GARANTIAS DE COMERCIABILIDADE,
ADEQUAÇÃO A UM FIM ESPECÍFICO E NÃO VIOLAÇÃO. EM NENHUM CASO O
Os autores ou detentores dos direitos autorais não serão responsabilizados por quaisquer reclamações, danos ou outros prejuízos.
RESPONSABILIDADE, SEJA EM AÇÃO CONTRATUAL, EXTRACONTRATUAL OU DE OUTRA NATUREZA, DECORRENTE DE,
DECORRENTE OU EM CONEXÃO COM O SOFTWARE OU O USO OU OUTRAS NEGOCIAÇÕES NO
SOFTWARE.
