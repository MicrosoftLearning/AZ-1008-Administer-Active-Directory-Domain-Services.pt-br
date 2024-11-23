---
lab:
  title: Exercício – Gerenciar políticas de senha
  module: Guided Project – Administer Active Directory Domain Services
---
Neste exercício, você configura itens de política de grupo relacionados a políticas de senha. Isso inclui configurar a política de senha de domínio, criar uma política de senha mais rigorosa para o grupo Administradores de Domínio e habilitar a Lixeira do Active Directory.

## Configurar uma política de senha de domínio

Nesta tarefa, você configurará a política de senha de domínio. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, no menu Ferramentas do console do Gerenciador de Servidores, abra o console de Gerenciamento de política de grupo.
2.  No console de Gerenciamento de política de grupo, expanda a floresta tailwindtraders.internal, a pasta Domínios e o domínio tailwindtraders.internal.
3.  Clique com o botão da direita do mouse em **Política de Domínio Padrão** e, em seguida, clique em **Editar**.
4.  No Editor de Gerenciamento de Política de Grupo, navegue até Configuração de computador\\Pol[iticas\\Configurações do Windows \\Configurações de segurança\\Pol[iticas de conta\\Pol[itica de senha.
5.  Clique duas vezes no item **Política de comprimento mínimo de senha**.
6.  Altere o número mínimo de caracteres para `14`.
7.  Clique em **OK** e feche a janela do Editor de Gerenciamento de Política de Grupo.
8.  Feche o console Gerenciamento de Política de Grupo.

## Configurar uma política de senha refinada

Nesta tarefa, você configurará uma política de senha refinada e a aplicará ao grupo Administradores de Domínio. Para executar esta tarefa, conclua as etapas a seguir em TAILWIND-DC1:

1.  No menu Ferramentas do console do Gerenciador de Servidores, abra o Centro Administrativo do Active Directory.
2.  Em Visão geral, clique em **Tailwindtraders (local)**.
3.  No painel tailwindtraders (local), abra o contêiner Sistema.
4.  No contêiner Sistema, abra o Contêiner de configuração de senha.
5.  Clique com o botão direito do mouse no Contêiner de configurações de senha, clique em **Novo** e então, clique em **Configurações de senha**.
6.  No campo Nome, digite `Domain Admin Password Policy`.
7.  Defina o campo Precedência como `1`.
8.  Defina o comprimento mínimo da senha como `16`.
9.  Clique em **OK.**
10. Abra a nova política **Política de senha de administradores de domínio**.
11. Na seção Aplica-se diretamente a, clique em **Adicionar** e digite `Domain Admins`. Clique em **Verificar Nomes** e depois em **OK**.
12. Clique em **OK.**

## Habilitar a Lixeira do Active Directory

Nesta tarefa, você habilitará a Lixeira do Active Directory. Para executar esta tarefa, conclua as etapas a seguir em TAILWIND-DC1:

1.  No menu Ferramentas do console do Gerenciador de Servidores, abra o Centro Administrativo do Active Directory.
2.  Clique em **Tailwindtraders (local)** no painel esquerdo.
3.  No painel à direita, selecione **Habilitar Lixeira**.
4.  Clique em **OK** para ignorar o aviso.
5.  Clique em **OK** para ignorar o aviso sobre a latência de replicação.
