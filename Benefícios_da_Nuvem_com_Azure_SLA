# Benefícios da Nuvem com Azure

O Microsoft Azure oferece uma série de benefícios ao utilizar a nuvem, proporcionando flexibilidade, escalabilidade e confiabilidade. Um dos aspectos mais importantes a serem considerados ao usar a nuvem é o **Acordo de Nível de Serviço** (SLA, _Service Level Agreement_), que define a disponibilidade garantida para os serviços. 
##  SLA

O SLA é um contrato formal que especifica a garantia de tempo de atividade de um serviço ou recurso no Azure. O tempo de atividade refere-se ao percentual de tempo que o serviço estará disponível para uso. O Azure oferece SLAs variados para diferentes serviços, com percentuais que podem chegar a 99,99% de disponibilidade. Com essa garantia, as empresas podem planejar melhor suas operações e minimizar o impacto de possíveis interrupções. Vale lembrar que quatos mais 9 após a virgula, menos tempo o serviço poderá permanecer indisponível, e isso não quer dizer que ele irá constatemente permanecer indisponível por esse tempo.

###  Como Definir o SLA de Acordo com as Necessidades

Em geral, as empresas podem adotar as seguintes diretrizes:

- **Crítico para o negócio**: Para serviços que não podem ficar fora do ar, como sites de e-commerce ou sistemas bancários, recomenda-se um SLA de 99,99% ou mais.
- **Serviços intermediários**: Para serviços importantes, mas que toleram um pequeno tempo de inatividade, um SLA de 99,95% pode ser adequado.
- **Serviços de baixa criticidade**: Para serviços internos ou de baixa utilização, um SLA de 99,9% pode ser suficiente.

No Azure, a escolha do SLA geralmente envolve a escolha correta de recursos, como redundância, disponibilidade geográfica e tipos de infraestrutura.

##  Recursos que Afetam o SLA durante a Criação de uma VM

Durante a criação de uma Máquina Virtual no Azure, diversos fatores podem impactar o SLA final do serviço. Os principais recursos que afetam o SLA incluem:

- **Regiões de Disponibilidade (Availability Zones)**: Ao configurar sua VM em mais de uma zona de disponibilidade, o Azure pode garantir uma maior disponibilidade. O uso de múltiplas zonas pode elevar o SLA para 99,99%, uma vez que as VMs estarão protegidas contra falhas de datacenter.
  
- **Conjuntos de Disponibilidade (Availability Sets)**: As VMs agrupadas em conjuntos de disponibilidade garantem que, em caso de manutenção ou falha, o impacto seja minimizado, mantendo o SLA em um nível alto. 

- **Discos Gerenciados (Managed Disks)**: O uso de discos gerenciados pelo Azure, como discos premium SSD, garante uma maior taxa de disponibilidade. Discos premium oferecem maior desempenho e resiliência contra falhas em comparação aos discos padrão.

- **Backup e Recuperação de Desastres (Backup and Disaster Recovery)**: Implementar uma estratégia de backup e recuperação de desastres aumenta a proteção contra perda de dados e reduz o tempo de inatividade, mas pode também elevar o custo.

- **Escalabilidade Automática (Auto-Scaling)**: Ao configurar grupos de máquinas virtuais com escalabilidade automática, você pode garantir que sua aplicação mantenha o desempenho em picos de utilização e tenha maior resiliência em caso de falhas.
