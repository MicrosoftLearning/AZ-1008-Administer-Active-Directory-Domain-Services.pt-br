---
lab:
  title: Exercício – Configurar operações do controlador de domínio
  module: Guided Project – Administer Active Directory Domain Services
---
Nesse exercício, você promove um servidor a controlador de domínio, transfere uma função FSMO para o novo controlador de domínio, cria um site e adiciona uma sub-rede ao site.

## Instale os Serviços de Domínio do Active Directory (AD DS) e promova para Controlador de Domínio

Nesta tarefa, você promoverá o servidor membro TAILWIND-MBR1 para se tornar um controlador de domínio no domínio TAILWINDTRADERS. Para executar esta tarefa, conclua as etapas a seguir:

1.  Faça login no TAILWIND-MBR1 como administrador\\do TAILWINDTRADERS com a senha: `Pa55w.rdPa55w.rd`.
2.  No Gerenciador de Servidores, selecione o menu Gerenciar e então, selecione **Adicionar funções e recursos**.
3.  Na página Antes de começar do assistente de "Adicionar funções e recursos", clique em **Avançar**.
4.  Na página Selecionar tipo de instalação, selecione **Instalação baseada em função ou em recurso** e clique em **Avançar**.
5.  Na página Selecionar servidor de destino, escolha **Selecionar um servidor no pool de servidores**, certifique-se de que TAILWIND-MBR1está selecione, e clique em **Avançar**.
6.  Na página Selecionar funções de servidor, selecione a caixa de seleção **Active Directory Domain Services**. Isso abre a página "Adicionar recursos". Selecione **Adicionar Recursos**. Clique em **Avançar**.
7.  Na página Selecionar recursos, clique em **Avançar**.
8.  Na página Active Directory Domain Services, clique em **Avançar**.
9.  Na página Confirmar seleções da instalação, clique em **Instalar**. Dependendo da velocidade do computador, a instalação pode levar vários minutos. Quando a instalação for concluída, clique em **Fechar**.
10. No menu Gerenciador de servidores, selecione o ícone de notificação ao lado da bandeira no canto superior direito (conforme mostrado na captura de tela).

    ![Captura de tela do menu do gerenciador de servidores com o ícone de alerta exibido.](./Media/server-manager-menu.png)
13. No menu que é aberto quando você seleciona o ícone de notificação, selecione **Promover este servidor a um controlador de domínio**. Isso iniciará o Assistente de Configuração do Active Directory Domain Servies.
14. Na página Configuração de implantação, selecione **Adicionar um controlador de domínio a um domínio existente** e verifique se o nome de domínio está definido como **tailwindtraders.internal**.
15. Você deve autenticar novamente a conta de administrador. Selecione **Alterar**. Insira o nome de usuário `Administrator` e a senha `Pa55w.rdPa55w.rd`. Clique em **OK.** Clique em **Avançar**.
16. Ná página de opções do controlador de domínio, use os valores padrão e defina uma senha do DSRM (Modo de restauração de Serviços de Diretório). Para fazer isso, digite a seguinte senha duas vezes: `Pa55w.rdPa55w.rd`. Clique em **Avançar**.
17. Na página Opções de DNS, clique em **Avançar**.
18. Na página Opções adicionais, clique em **Avançar**.
19. Na página Caminhos, clique em **Avançar**.
20. Na página Revisar opções, clique em **Avançar**.
21. Na página Verificação de pré-requisitos, clique em **Avançar**. A instalação levará vários minutos, dependendo da velocidade da máquina virtual. A máquina virtual será reiniciada.
22. Quando a máquina virtual for reiniciada, entre como `tailwindtraders\administrator` com a senha configurada para a conta de administrador padrão (`Pa55w.rdPa55w.rd`)

## Transferir funções flexíveis de operações mestre únicas

Nesta tarefa, você transferirá a função mestre RID de TAILWIND-DC1 para TAILWIND-MBR1. Para executar esta tarefa, conclua as etapas a seguir:

1.  No TAILWIND-MBR1, em **Ferramentas**, abra Usuários e Computadores do Active Directory.<br>
2.  No painel de navegação, clique com o botão direito do mouse em Usuários e Computadores do Active Directory, aponte para **Todas as tarefas** e clique em **Mestres de operações**.
3.  Na guia RID, selecione **Alterar**, selecione **Sim** e clique em **OK**.
4.  Clique em **Fechar** para fechar a caixa de diálogo Mestres de operações.

## Crie um site do Active Directory e configure uma sub-rede para esse site

Nessa tarefa, você criará um site do Active Directory e configurará uma sub-rede para esse site. Para executar esta tarefa, conclua as etapas a seguir:

1.  No TAILWIND-DC1, faça login como `tailwindtraders\administrator` com a senha configurada para a conta de administrador padrão (`Pa55w.rdPa55w.rd`).
2.  Abra os sites e serviços do Active Directory a partir do menu Ferramentas.
3.  Clique com o botão direito do mouse em Sites, selecione **Novo site** e digite `Sydney` como o nome do site.
4.  Para o Nome do link, selecione DEFAULTIPSITELINK e clique em **OK** duas vezes.
5.  Expanda a pasta **Sites**.
6.  Clique com o botão direito do mouse em **Sub-redes** e selecione **Nova Sub-rede**.
7.  Como prefixo, digite `172.16.1.0/24`, selecione **Sydney** como nome do site e clique em **OK**.
8.  Feche Sites e Serviços do Active Directory.
