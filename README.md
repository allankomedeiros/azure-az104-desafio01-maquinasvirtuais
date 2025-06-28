#Gerenciamento de Máquinas Virtuais no Azure - AZ-104

Este repositório faz parte do meu desafio do curso de preparação para certificação **AZ-104** na DIO.me. Aqui compartilho minhas anotações, resumos e dicas práticas sobre gerenciamento de máquinas virtuais no **Microsoft Azure**.

---

##Conteúdos abordados

###Resource Groups
- Usados para agrupar recursos relacionados.
- Permitem gerenciar custos, aplicar RBAC e policies de forma centralizada.
- Excluir o resource group apaga todos os recursos dentro dele.

###RBAC (Role-Based Access Control)
- Controle granular de permissões.
- Exemplo de roles:
  - **Owner:** controle total.
  - **Contributor:** cria e gerencia recursos, mas não gerencia permissões.
  - **Reader:** só leitura.
- Boa prática: sempre aplicar o princípio do menor privilégio.
- As permissões podem ser dadas ao resource group, na assinatura ou no recurso.

###Azure Policy
- Garantem compliance e governança.
- É normal comparar com o ambiente on premise - GPO
-Casos de uso:
  -Tipos de recursos permitidos - definir padrões de recursos
  -Definir quais o locais permitidos para criação dos recursos
  -Exigir tag e seu valor
-A política é aplicado a todos, independente do permissionamento
-Pode ser criado política de remediação
  -Exemplo: Pode ser alterado o valor de todas as referência das tags

###VNet e Peering
- VNet é a rede virtual do Azure, equivalente a LAN no datacenter.
- **Peering** conecta VNets, permitindo comunicação sem VPN.
- [Modelo ARM de VNet criada nos laborátórios práticos](./arm/vnet-template.json)
- [Modelo BICEPS de VNet criada nos laborátórios práticos](./biceps/vnet-template.biceps)
  
###NSG e ASG
- **NSG (Network Security Group):** controla tráfego para subnets ou NICs.
- **ASG (Application Security Group):** agrupa VMs por função, facilitando regras no NSG.
- 

###Storage Accounts
- Usado para armazenar blobs, files, tables e queues.
- Ideal para backups, imagens de VM e dados de app.

