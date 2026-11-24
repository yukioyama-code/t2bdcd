# Trabalho 2 - BDCD - Coautoria parlamentar no Neo4j
Banco de Dados para Ciência de Dados
Carolina Megumi Nogai | 834418
Yuki Hiroji Oyama | 830916

O projeto analisa a participação de deputados na autoria de projetos de lei apresentados em 2025, incluindo a colaboração entre partidos. Os dados são do [Portal de Dados Abertos da Câmara dos Deputados](https://dadosabertos.camara.leg.br/swagger/api.html).

## Arquivos

| Arquivo | Conteúdo |
| --- | --- |
| `deputados.csv` | Cadastro de deputados. |
| `proposicoes-2025.csv` | Proposições do arquivo anual da Câmara. |
| `proposicoesAutores-2025.csv` | Registros de autoria e siglas partidárias. |
| Script `.cypher` | Consultas usadas no trabalho. |

## Como reproduzir

1. Abra uma instância local no **Neo4j Desktop**.
2. Na aba **Import**, carregue os três CSVs. Use `deputados.csv` para o nó `Deputado` e `proposicoes-2025.csv` para o nó `Proposições`.
3. Use `proposicoesAutores-2025.csv` para mapear a relação `AUTOR_DE`. Na origem, associe `uriAutor` à propriedade `uri` de `Deputado`. No destino, associe `idProposicao` à propriedade `id` de `Proposições`. Inclua `siglaPartidoAutor` como propriedade da relação.
4. Execute a importação e rode o script na aba **Query**, no mesmo banco. Nas consultas sobre projetos de lei, o recorte usa `siglaTipo` e `dataApresentacao`.

