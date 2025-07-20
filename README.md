# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

Data: 20/07/2025
Empresa: Abstergo Industries 
Responsável: Hugo Porto

## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa [nome da empresa], realizado por Hugo Porto. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar redução de custos imediatos.

## Descrição do Projeto
O projeto de implementação das ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. A seguir, serão descritas as etapas do projeto:

## 1. Etapa
### <img src="https://www.meiro.io/_next/image/?url=https%3A%2F%2Fres.cloudinary.com%2Fdnxlpdalu%2Fimage%2Fupload%2Fv1730897447%2FIntegration_aurora_alt_36d735df6c.png&w=640&q=75" width=88px align="center"/> AURORA DB 


* **Objetivo:** Controle de estoque em tempo real, gestão de informações, compatibilidade com ferramentas para geração de relatórios (Analytics) e confiabilidade das informações dado a necessidade de Compliance (ANVISA E LGPD.

* **Descrição de caso de uso:** Os produtos são cadastrados via sistema, em suas respectivas tabelas conforme definições para o banco de dados, com suas informações referentes à SKU, DCB (Denominação Comum Brasileira) para anvisa, nome, quantidade, preço, validade e etc.
Mediante a ocorrência de cadastro de novo produto, após uma venda ou entrada de produto em estoque a atualização do sistema é realizada em tempo real para os demais usuários garantindo assim que não haja excesso ou falta de produtos já que o sistema pode calcular automáticamente a nova demanda por meio de triggers e procedures dado que o AURORA pode realizar query complexas tal qual MYSQL e POSTGRESql.


## 2. Etapa
### <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bc/Amazon-S3-Logo.svg/428px-Amazon-S3-Logo.svg.png?20220427001138" width=60px align="center"/>  AMAZON S3
* **Objetivo:** Armazenamento de informações estáticas como imagens, documentos de texto (PDFs) como bulas, FISPQS, notas fiscais, receitas médicas e etc.

* **Descrição de caso de uso:** Dentro do Bucket-S3 podem ser inseridas informações estáticas altamente gerenciáveis (podem ser para uso diário, bem como backups). O bucket S3 ainda possui o recurso de atribuir TAGs customizadas facilitando ainda mais a rastreabilidade da informação, uma vez que essa TAG pode fazer parte de um dos campos das tabelas dos produtos. Durante o cadastro dos produtos e medicamentos podem ser anexadas nas tabelas do banco de dados suas referências (TAGs) das imagens e documentos, uma vez que o bucket S3 possui links (url única no mundo todo) para cada elemento armazenado no bucket. 

## 3. Etapa
### <img src="https://img.icons8.com/color/512/awslambda.png" width=80px align="center"/> AWS LAMBDA
  
* **Objetivo:** Automatizar processos (apenas via código de programação) sem necessidade de servidores.
* **Descrição de caso de uso:** O AWS LAMBDA é uma ferramenta que permite disparar um evento ou ação assim que uma condição é satisfeita. Exemplo: a partir do momento em que ocorre uma venda em uma das farmácias da rede e é indicado que o produto atingiu seu estoque mínimo, a função criada para atualizar o estoque é disparada e a equipe responsável pela reposição é rapidamente informada por meio de mensagens ou email sobre o evento ocorrido.


## Conclusão
A implementação das ferramentas Cloud na empresa Abstergo Industries tem como objetivo a redução de custos e erros operacionais, aumentando a produtividade da empresa, bem como a adequação a legislações governamentais de saúde.

## Quadro Analítico
   Descrição    |       Aplicação         |       Benefício                 |
|:-----------------------|:-------------------------|:----------------------------|
|AURORA DB 		|	Gerenciamento de estoque em tempo real			|	Velocidade, Compliance e escalabilidade|
|S3				|Armazenamento de imagens, documentos e backups		|Acessibilidade.|
|Lambda			|	Automação de processos (notificações e relatórios)	|	Redução de custos com servidores e automação|

Assinatura do Responsável pelo Projeto:
Hugo Porto