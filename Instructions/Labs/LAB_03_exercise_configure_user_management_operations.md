---
lab:
  title: 'Exercício – Configurar operações de gerenciamento de usuários '
  module: Guided Project – Administer Active Directory Domain Services
---
Nesse exercício, você executa operações de gerenciamento de usuários.

## Criar unidades organizacionais

Nesta tarefa, você criará três UOs: Sydney, Melbourne e Brisbane. Para executar esta tarefa, conclua as etapas a seguir:

1.  No TAILWIND-DC1, abra Usuários e Computadores do Active Directory no menu Ferramentas do console do Gerenciador de servidores.
2.  Clique com o botão direito do mouse no domínio **tailwindtraders.internal**.
3.  Selecione **Novo** e selecione **unidade organizacional**.
4.  Na caixa de diálogo Novo Objeto - Unidade Organizacional, defina o nome como `Sydney` e clique em **OK**.
5.  Repita esse processo para criar a UO `Melbourne` e a UO `Brisbane`.

## Criar usuários

Nesta tarefa, você criará um usuário e configurará as propriedades da conta, como a data de vencimento da conta. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, abra Usuários e Computadores do Active Directory (ou Centro Administrativo).
2.  Clique com o botão direito do mouse na UO Sydney.
3.  Selecione **Novo**, e em seguida **Usuário**.
4.  Digite `SydneyContractor` nos campos Nome completo e Nome de logon do usuário e clique em **Avançar**.
5.  Especifique uma senha, como `Pa55w.rdPa55w.rd`, e confirme a senha.
6.  Clique em **Avançar** e **Concluir**.
7.  Selecione a UO Sydney. Na UO Sydney, clique duas vezes na conta de usuário SydneyContractor.
8.  Na guia Conta, na seção **A conta expira**, selecione **Fim de:** e defina a data como **1º de janeiro de 2030**. Clique em **OK.**
9.  Clique com o botão direito do mouse no usuário SydneyContractor e selecione **Copiar**.
10. Digite `MelbourneContractor` nos campos Nome completo e Nome de logon do usuário. Clique em **Avançar**.
11. Especifique uma senha, como `Pa55w.rdPa55w.rd` e confirme a senha.
12. Clique em **Avançar** e **Concluir**.
13. Clique com o botão direito do mouse no usuário SydneyContractor e selecione **Copiar**.
14. Digite `BrisbaneContractor` nos campos Nome completo e Nome de logon do usuário. Clique em **Avançar**.
15. Especifique uma senha, como `Pa55w.rdPa55w.rd` e confirme a senha.
16. Clique em **Avançar** e **Concluir**.
17. Arraste o usuário MelbourneContractor para a UO Melbourne.
18. Se um aviso sobre movimentar objetos for exibido, clique em **Sim**.
19. Arraste o usuário BrisbaneContractor para a UO Brisbane.
20. Se um aviso sobre movimentar objetos for exibido, clique em **Sim**.


## Crie o grupo Administradores de Sydney

Nesta tarefa, você criará um novo grupo de segurança chamado Administradores de Sydney. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, abra Usuários e Computadores do Active Directory.
2.  Clique com o botão direito do mouse na UO, selecione **Novo** e selecione **Grupo**.
3.  Digite `Sydney Administrators` no Nome do grupo e selecione **Universal** no escopo do grupo. Clique em **OK.**
4.  Na UO Sydney, clique duas vezes na conta de usuário SydneyContractor.
5.  Na guia Membro de, clique em **Adicionar**.
6.  Digite `Sydney Administrators`.
7.  Clique em **Verificar Nomes**.
8.  Clique em **OK** e clique em **OK** novamente.

## Configurar um usuário como usuário protegido

Nesta tarefa, você configurará a conta de usuário SydneyContractor como um usuário protegido. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, abra Usuários e Computadores do Active Directory (ou Centro Administrativo).
2.  Navegue até a UO Sydney e clique duas vezes na conta de usuário SydneyContractor.
3.  Na guia Membro de, clique em **Adicionar**.
4.  Digite `Protected Users`.
5.  Clique em **Verificar Nomes**.
6.  Clique em **OK** e clique em **OK** novamente.

## Delegar permissões de segurança de uma unidade organizacional para um grupo de segurança

Nesta tarefa, você delegará a capacidade de redefinir senhas e forçar a alteração de senha ao grupo Administradores de Sydney em contas na UO Sydney. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, abra Usuários e Computadores do Active Directory.
2.  Clique com o botão direito do mouse na UO Sydney e clique em **Delegar Controle**.
3.  Na página inicial do Assistente de delegação de controle, clique em **Avançar**.
4.  Clique em **Adicionar** e digite `Sydney Administrators`.
5.  Clique em **Verificar Nomes**.
6.  Clique em **OK** e clique em **Avançar**.
7.  Na página Tarefas para delegar, selecione a opção **Redefinir senhas de usuário e forçar a alteração de senha no próximo logon**. Clique em **Próximo**.
8.  Clique em **Concluir**.

## Configurar atributo de cidade para um usuário

Nesta tarefa, você configurará um atributo de cidade para uma conta de usuário e, em seguida, usará o atributo Localizar para verificar se o usuário está presente. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, abra Usuários e Computadores do Active Directory.
2.  Selecione a UO Sydney, clique com o botão direito do mouse na conta de usuário SydneyContractor e clique em **Propriedades**.
3.  Na guia Endereço das propriedades de prestador de serviço de Sydney, defina o campo Cidade como `Sydney` e clique em **OK**.
4.  Em Usuários e Computadores do Active Directory, clique com o botão direito do mouse em Tailwindtrader.internal e clique em **Localizar**.
5.  Na guia Avançado da caixa de diálogo Localizar usuários, contatos e grupos, selecione **Campo**, **Usuário** e **Cidade**. Defina a Condição como **É (exatamente)**. Defina o Valor como **Sydney**. Clique em **Localizar Agora**.
6.  Clique em **Sim** no pop-up Localizar no diretório.
7.  Verifique se o usuário SydneyContractor está listado nos **resultados da pesquisa**.
8.  Feche a caixa de diálogo Localizar usuários, contatos e grupos.

## Desabilitar o usuário do contratante Melbourne

Nesta tarefa, você desativará o usuário do MelbourneContractor. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, abra Usuários e Computadores do Active Directory e, em seguida, abra a UO Melbourne.
2.  Na UO Melbourne, clique com o botão direito do mouse em **MelbourneContractor** e clique em **Desativar conta**.
3.  Clique em **OK.**

## Redefinir a senha do usuário do contratante Brisbane

Nesta tarefa, você reconfigurará a senha do usuário BrisbaneContractor. Para executar esta tarefa, conclua as etapas a seguir:

1.  Em TAILWIND-DC1, abra Usuários e Computadores do Active Directory e, em seguida, abra a UO Brisbane.
2.  Clique com o botão direito do mouse no usuário BrisbaneContractor e selecione **Redefinir senha**.
3.  Na caixa de diálogo Redefinir senha, digite a senha `Pa66w.rdPa66w.rd` duas vezes e selecione **OK**. Clique em **OK** novamente na caixa de diálogo que notifica que a senha foi alterada.
