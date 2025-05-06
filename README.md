
# 📘  Criação de uma Instância Gerenciada de SQL do Azure

Este documento tem como objetivo orientar sobre os pré-requisitos e o processo para criar uma **Instância Gerenciada de SQL do Azure**, utilizando o **portal do Azure**.


## ✅ Pré-requisitos

Antes de começar, certifique-se de possuir os seguintes itens:

- Uma assinatura ativa do **Microsoft Azure**.  
  > Se você ainda não possui uma conta, pode criar uma conta gratuita do Azure (https://azure.microsoft.com/free/).


## 🧩 Sobre a Instância Gerenciada de SQL do Azure

A **Instância Gerenciada de SQL do Azure** é uma solução de banco de dados totalmente gerenciada que oferece alta disponibilidade, escalabilidade automática e recursos avançados de segurança. É ideal para migrações de bancos SQL Server locais com mínima alteração no código.

Durante a implantação, tenha em mente:

- O processo de provisionamento pode ser cancelado via portal, PowerShell, CLI ou API REST.
- A implantação pode sofrer atrasos se houver outras operações em andamento na mesma sub-rede (ex: restauração longa ou redimensionamento).
- Para visualizar a instância no grupo de recursos, é necessário ter permissões de leitura no mesmo.

## 🔧 Como Criar a Instância Gerenciada no Portal do Azure

### Passo 1: Acessar o Portal do Azure
1. Acesse o Portal do Azure (https://portal.azure.com) e faça login com suas credenciais.

2. No menu esquerdo, selecione **SQL do Azure**.  
   > Caso não encontre, clique em **Todos os serviços** e pesquise por "SQL do Azure".

3. Clique no botão `+ Criar`.

4. Na página **Selecionar opção de implantação do SQL**, selecione a opção **Instância Gerenciada de SQL** e clique em **Mostrar detalhes**.

5. Escolha **Instância única** e clique em **Criar** para abrir o formulário de criação da instância.


### Passo 2: Preencher Informações Básicas

Na aba **Básico**, preencha as seguintes informações:

- **Assinatura**: Selecione a assinatura desejada.
- **Grupo de recursos**: Crie um novo ou selecione um existente.
- **Nome da instância gerenciada**.
- **Região**: Escolha uma região compatível.
- **Tipo de preço**: Defina conforme necessidade (pode ser configurado posteriormente).

> Após concluir, clique em **Próximo: Computação + armazenamento**.


### Passo 3: Configurar Computação + Armazenamento

Clique em **Configurar instância gerenciada** para ajustar:

- Tamanho de computação (vCores e geração)
- Armazenamento total disponível
- Redundância de backup

> Após definir as configurações, clique em **Aplicar** e depois em **Próximo: Rede**.


### Passo 4: Configurar Rede

Nesta etapa, defina:

- Rede virtual e sub-rede dedicada para a instância.
- Zonas de disponibilidade (opcional).
- Endereço IP público (opcional, dependendo do cenário).

> Você pode deixar os valores padrão se desejar, mas recomenda-se revisar para garantir conformidade com sua arquitetura de rede.

> Clique em **Próximo: Segurança** ou **Próximo: Marcas** para continuar.


### Passo 5: (Opcional) Configurações Avançadas

#### Segurança
- Configure autenticação e auditoria.
- Integre com Key Vault, se necessário.

#### Marcas (Recomendado)
- Adicione tags organizacionais (departamento, projeto, ambiente, etc.).


### Passo 6: Revisão Final e Criação

1. Clique em **Revisar + criar** para validar todas as configurações.
2. Corrija qualquer erro apontado.
3. Após a validação bem-sucedida, clique em **Criar** para iniciar o processo de provisionamento.

> ⏱️ A implantação pode levar alguns minutos.


## 📌 Observações Finais

- Mantenha sempre permissões atualizadas no grupo de recursos.
- Monitore o status da implantação através do painel de notificações do Azure.
- Considere documentar e padronizar nomes, regiões e configurações para facilitar gestão futura.


## 📚 Recursos Adicionais
- https://learn.microsoft.com/pt-br/azure/azure-sql/managed-instance/instance-create-quickstart?view=azuresql&tabs=azure-portal

