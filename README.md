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

# Maquinas Virtuais
Antes de criar uma **Máquina Virtual (VM)** na Azure, é necessário configurar alguns recursos de suporte para garantir que a VM funcione corretamente. Esses recursos fornecem infraestrutura, conectividade e segurança para a VM.

1. **Criar o Grupo de Recursos**: Um contêiner lógico que agrupa todos os recursos associados à VM.
2. **Criar a VNet e Sub-rede**: A rede virtual e a sub-rede onde a VM será implantada.
3. **Configurar o NSG**: Definir regras de firewall para controlar o tráfego.
4. **Associar ou Criar Endereço IP Público** (opcional): Para acesso remoto à VM.
5. **Criar o Disco do Sistema Operacional**: Necessário para a inicialização da VM.
6. **Configurar Identidade Gerenciada** (opcional): Para controle de acesso seguro a outros serviços da Azure.

Esses são os recursos essenciais que precisam ser configurados antes de criar uma VM na Azure.

## Feito isto devemos criar seguindo este passo

##  Crie um Novo Recurso
- **Passo**: No menu à esquerda, clique em **Criar um recurso**.
- **Descrição**: O Azure oferece uma vasta gama de recursos, como VMs, redes, armazenamento e muito mais.

##  Selecione o Serviço de Máquina Virtual
- **Passo**: No campo de busca ou em **Computação**, selecione **Máquina Virtual**.
- **Descrição**: Isso abrirá o assistente de criação de VMs, onde você poderá configurar os detalhes da sua VM.

##  Configuração Básica
- **Passo**: No primeiro passo do assistente, preencha as seguintes informações:
    - **Assinatura**: Selecione a assinatura de Azure que será usada.
    - **Grupo de Recursos**: Crie um novo ou selecione um grupo de recursos existente.
    - **Nome da VM**: Defina um nome para a sua máquina virtual.
    - **Região**: Escolha a região onde a VM será hospedada (ex.: East US, West Europe).
    - **Imagem**: Escolha o sistema operacional da VM (ex.: Ubuntu, Windows Server).
    - **Tamanho**: Escolha o tamanho da VM (número de CPUs, memória). Use "Ver todos os tamanhos" para mais opções.
    - **Usuário de Admin**: Defina o nome de usuário e senha (ou chave SSH) para acessar a VM.

##  Configuração de Disco
- **Passo**: Na aba **Discos**, configure o disco da VM:
    - **Disco do SO**: Escolha o tipo de disco para o sistema operacional (SSD premium, SSD padrão ou HDD).
    - **Discos de Dados**: Opcionalmente, anexe discos adicionais para armazenar dados.

##  Configuração de Rede
- **Passo**: Na aba **Rede**, configure os parâmetros de rede:
    - **Rede Virtual**: Crie ou selecione uma rede virtual (VNet).
    - **Sub-rede**: Selecione ou crie uma sub-rede dentro da VNet.
    - **Endereço IP Público**: Se precisar acessar a VM pela internet, selecione **Sim** para configurar um IP público.
    - **Grupo de Segurança de Rede (NSG)**: Escolha **Básico** e permita as portas necessárias, como **22** para SSH (Linux) ou **3389** para RDP (Windows).

##  Configurações Avançadas (opcional)
- **Passo**: Na aba **Gerenciamento**, ajuste opções como:
    - **Monitoramento**: Habilite ou desabilite o diagnóstico de inicialização e monitoramento do sistema.
    - **Identidade Gerenciada**: Se a VM precisar acessar outros serviços da Azure, habilite a identidade gerenciada.

##  Revisar e Criar
- **Passo**: Clique em **Revisar + Criar**.
- **Descrição**: O Azure validará as configurações. Se tudo estiver correto, você verá uma tela de resumo.
- **Ação**: Clique em **Criar** para iniciar a implantação da VM.

##  Acompanhe a Implantação
- **Passo**: Acompanhe o progresso da criação da VM na tela de **Notificações** ou na página do **Grupo de Recursos**.
- **Descrição**: A implantação pode levar alguns minutos. Uma vez concluída, a VM estará pronta para ser usada.

##  Acessando a VM
- **Passo**: Após a criação, acesse a VM da seguinte maneira:
    - **Linux**: Use um cliente SSH para conectar à VM (com o endereço IP público ou DNS público).
    - **Windows**: Use o Remote Desktop Protocol (RDP) para se conectar à VM.
