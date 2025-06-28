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

###Azure Policy
- Garantem compliance e governança.
- Exemplo: bloquear criação de VMs fora do Brasil ou exigir tag “Environment”.

###VNet e Peering
- VNet é a rede virtual do Azure, equivalente a LAN no datacenter.
- **Peering** conecta VNets, permitindo comunicação sem VPN.

###NSG e ASG
- **NSG (Network Security Group):** controla tráfego para subnets ou NICs.
- **ASG (Application Security Group):** agrupa VMs por função, facilitando regras no NSG.

###Storage Accounts
- Usado para armazenar blobs, files, tables e queues.
- Ideal para backups, imagens de VM e dados de app.

###Monitoramento com Azure Monitor e Log Analytics
- Azure Monitor coleta métricas e logs.
- Log Analytics permite queries avançadas com Kusto Query Language (KQL).

###Backup e Recovery
- Recovery Services Vault gerencia backups e pontos de restauração.
- Protege VMs, bancos SQL e outros recursos.

###Azure CLI e PowerShell
- Automatizam deploys e gerenciamento.
- Exemplo para criar uma VM:

```bash
az vm create \
  --resource-group MeuRG \
  --name MinhaVM \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys
