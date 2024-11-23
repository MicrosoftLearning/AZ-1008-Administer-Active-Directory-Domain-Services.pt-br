---
lab:
  title: Exercício – Definir as configurações de segurança
  module: Guided Project – Administer Active Directory Domain Services
---
Nesse exercício, você define configurações relacionadas à segurança, incluindo desabilitar a autenticação NTLM para contas de domínio, auditar atividades de gerenciamento de contas e negar logon como um serviço para membros de um grupo de segurança.

## Restringir autenticação NTLM

Nesta tarefa, você restringirá a autenticação NTLM. Para executar esta tarefa, conclua as etapas a seguir em TAILWIND-DC1:

1.  No menu Ferramentas do console do Gerenciador do Servidor, abra o console Gerenciamento de política de grupo.
2.  No console de Gerenciamento de política de grupo, expanda a floresta tailwindtraders.internal, a pasta Domínios e o domínio tailwindtraders.internal. Em seguida, expanda os objetos de política de grupo.
3.  Clique com botão direito na **Política de controlador de domínio padrão** e clique em **Editar**.
4.  Navegue até Configuração do computador\\Políticas\\Configurações do Windows\\Configurações de segurança\\Políticas Locais\\Opções de segurança.
5.  Selecione e clique duas vezes com o botão direito do mouse em **Segurança de rede: Restringir NTLM: autenticação NTLM neste domínio**.
6.  Marque a caixa de seleção **Definir estas configurações de política**.
7.  Selecione o valor **Negar tudo** e clique em **OK**.
8.  clique em **Sim** na caixa de diálogo Confirmar alteração da configuração.
9.  Feche o Editor de Gerenciamento de Política de Grupo.

## Auditoria de gerenciamento de contas de usuários em Sydney

Nesta tarefa, você habilita a auditoria do Gerenciamento de conta de usuário da UO Sydney. Para executar esta tarefa, conclua as etapas a seguir em TAILWIND-DC1:

1.  No menu Ferramentas do console do Gerenciador do Servidor, selecione Console de gerenciamento de política de grupo.
2.  No Console de gerenciamento de política de grupo, expanda o domínio Tailwindtraders.internal.
3.  Navegue até a UO Sydney, clique com o botão direito do mouse e selecione **Criar um GPO neste domínio e fornecer um link para ele aqui...**.
4.  Dê o nome `SydneyOUPolicy` ao novo GPO
5.  Clique em **OK**
6.  Clique com o botão direito do mouse em SydneyOUPolicy e selecione **Editar**.
7.  Navegue até Configuração do Computador\\Políticas\\Configurações do Windows\\Configurações de segurança\\Configuração de política de auditoria avançada\\Políticas de auditoria\\Gerenciamento de conta.
8.  Selecione e clique duas vezes com o botão direito do mouse em **Gerenciamento de conta do usuário de auditoria**.
9.  Selecione a caixa de seleção **Configurar os seguintes eventos de auditoria**.
10.  Selecione os valores **Êxito** e **Falha** e clique em **OK**.
11.  Feche o Editor do gerenciamento de política de grupo

## Negar logon como serviço

Nesta tarefa, você configurará a opção de segurança Negar logon como serviço. Para executar esta tarefa, conclua as etapas a seguir em TAILWIND-DC1:

1.  No menu Ferramentas do console do Gerenciador do Servidor, abra o console Gerenciamento de política de grupo.
2.  Expanda o domínio Tailwindtraders.internal.
3.  Navegue até a UO Sydney e clique com o botão direito do mouse em SydneyOUPolicy. Selecione **Editar**.
4.  Navegue até Configuração do Computador\\Políticas\\Configurações do Windows\\Configurações de segurança\\Políticas locais\\Atribuição de direitos de usuário.
5.  Selecione e clique duas vezes na política **Negar logon como um serviço**.
6.  Selecione a configuração **Definir esta política**.
7.  Clique em **Adicionar Usuário ou Grupo**.
8.  Clique em **Procurar**, **Avançado** e depois, em **Localizar agora**.
9.  Selecione o grupo **Administradores de Sydney**.
10. Clique em **OK** até que as caixas de diálogo sejam fechadas (pode exigir quatro ou cinco confirmações).
