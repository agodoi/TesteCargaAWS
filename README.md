# Computação Ágil e Elástica (parte prática - como medir)

Neste encontro iremos abordar o crescimento extremo e exponencial de acesso aos serviços e aplicações na nuvem e como sua arquitetura deve ser desenhada de forma a atender esta demanda crescente de acessos. Serão apresentados os 6 R"s da Migração e o Well-Architected Framework da AWS. Iremos compreender os conceitos de elasticidade, escalabilidade e alta disponibilidade no contexto da nuvem e como mitigar possíveis ataques como DDoS. Realizar testes de carga para verificar escalabilidade do sistema.

## Objetivos

* Subir 2 EC2: um bastion host e um EC2 como servidor interno
* Adicionar o ELB
* Adicionar o serviço de Auto Scalling
* Instalar o K6 no bastion host
* Gerar tráfego do bastion para o EC2

## Impactos no seu projeto

Sua aplicação da Vivo, especialmente o RDS, precisa ter recursos de auto scalling e gestão na carga entre os computadores internos. A instrução de hoje ensina como fazer isso.

## Não faça

* Qualquer tentativa de ter 20 ou mais instâncias em execução simultânea (seja qual for o tamanho) causará a desativação imediata da conta da AWS e todos os recursos na conta serão excluídos imediatamente;

* Testes K6 usando o seu computador do Inteli para o servidor EC2 dentro da sua VPC;

* Testes de outro sites, como o do Inteli, pois vc será banido e vai arrumar um problemão;

## Conceitos

O Elastic Load Balancing distribui automaticamente o tráfego de entrada das aplicações por várias instâncias do Amazon EC2. Ele permite obter tolerância a falhas nos aplicativos por meio da disponibilização sem problemas da capacidade necessária de balanceamento de carga para rotear o tráfego de aplicativos.

O Auto Scaling ajuda a manter a disponibilidade da aplicação e permite aumentar ou reduzir a capacidade do Amazon EC2 de forma automática, de acordo com condições definidas por você. Você pode usar o Auto Scaling para ajudar a garantir que está executando o número desejado de instâncias Amazon EC2. O Auto Scaling também pode aumentar automaticamente o número de instâncias do Amazon EC2 durante picos de demanda para manter o desempenho, e diminuir a capacidade durante períodos ociosos para reduzir os custos. O Auto Scaling é ideal para aplicativos com padrões de demanda estáveis ou que passam por variações de utilização horárias, diárias ou semanais.

### Arquitetura Começa Assim:

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/TesteCargaAWS/blob/main/imgs/starting-architecture.png">
   <img alt="Arquitetura Inicial" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/TesteCargaAWS/blob/main/imgs/starting-architecture.png)">
</picture>

### Arquitetura Finaliza Assim:

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/TesteCargaAWS/blob/main/imgs/final-architecture.png">
   <img alt="Arquitetura Inicial" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/TesteCargaAWS/blob/main/imgs/final-architecture.png)">
</picture>



# Atenção
