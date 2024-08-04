# DESAFIO-BEEDOO<br><br>

[Plano de Testes](https://docs.google.com/spreadsheets/d/1w5yE3EWMGonjFGHuVk9z16AMYCi-kO6GkLVTQcBrsPc/edit?usp=sharing)<br>
[Bug Report](https://docs.google.com/spreadsheets/d/1slf5BBF518bXavaUtJ-q-lfvjbDRnR0buGHS7Mot_Ow/edit?usp=sharing)<br>
[Evidências](https://drive.google.com/drive/folders/1sfqNiMeHx_j6LVvvlyN9GBWGZlOdDCjo?usp=sharing)<br><br>

User Story 1: Criando um Curso<br>
Como administrator,<br>
Eu quero criar um novo curso,<br>
Para que eu possa oferecer treinamentos aos usuários.<br>
<br>
Critérios de aceite:<br>
•	Deverá existir botão para cadastrar novo curso;<br>
•	Na página de cadastramento, deve haver formulário com campos de nome do curso, descrição, nome do instrutor, URL da imagem de capa, data de inicio e de fim, número de vagas e o tipo de curso;<br>
•	O sistema deverá validar se todos os campos forma preenchidos corretamente;<br>
•	Ao salvar, deverá aparecer na lista de cursos.<br><br>

**Caso de uso**:	Criar Cursos<br>
**Objetivo**:	Criar cursos no sistema de cursos da Beedoo<br>
**Atores**:	Administrador<br><br>


 Regras de negócio  	 <br>
**RN01**: O título deve ter acima de 10 caracteres;<br>
**RN02**: A descrição do curso deve ter acima de 10 caracteres;<br>
**RN03**: O nome do instrutor deve ter no mínimo duas palavras;<br>
**RN04**: A URL da imagem de capa deve ser um link e retornar imagem;<br>
**RN05**: A data de inicio deve ser anterior à data de fim;<br>
**RN06**: O número de vagas devem ser números;<br>
**RN07**: O tipo de curso deve ser selecionado entre Online ou Presencial;<br>
**RN08**: Caso o curso seja presencial, o campo Endereço deve aparecer;<br>
**RN09**: O endereço deve conter mais de 10 caracteres.<br><br><br>



CT01<br>
Funcionalidade: Criar Curso<br><br>

  Cenário: Criar curso com sucesso<br>
    Dado que o administrador está na página de criação de curso<br>
    Quando ele preencher todos os campos obrigatórios corretamente<br>
    E clicar no botão de salvar<br>
    Então o curso deve ser criado<br>
    E o curso deve ser exibido na lista de cursos disponíveis<br><br>

  Cenário: Falha ao criar curso com campos obrigatórios em branco<br>
    Dado que o administrador está na página de criação de curso<br>
    Quando ele tentar salvar sem preencher todos os campos obrigatórios<br>
    Então o sistema deve exibir uma mensagem de erro<br>
    E a mensagem deve indicar os campos que precisam ser preenchidos<br><br>

  Cenário: Falha ao criar curso com data de início posterior à data de término<br>
    Dado que o administrador está na página de criação de curso<br>
    Quando ele preencher o campo de data de início com uma data posterior à data de término<br>
    E clicar no botão de salvar<br>
    Então o sistema deve exibir uma mensagem de erro indicando que a data de início deve ser anterior à data de término<br><br><br>




<br>
User Story 2: Visualizar Cursos e Excluir<br>
Como administrador,<br>
Eu quero visualizar os cursos,<br>
Podendo assim, ficar ciente de todos os cursos que ofertamos no momento e,<br>
Excluir cursos caso necessário.<br><br>

Critérios de Aceite:<br>
•	Deve existir o botão de Listar Cursos;<br>
•	Ao acessar a página, deve conter cada curso com imagem, o nome, descrição, se online ou presencial, a data de início e de fim, a quantidade de vagas e botão de excluir o curso;<br>
•	Ao clicar no botão excluir curso, deve aparecer mensagem para confirmar o evento;<br>
•	Ao concordar, aparece imagem de confirmação e o curso será excluído do sistema.
<br><br>

**Caso de uso**:	Visualizar e Excluir Cursos<br>
**Objetivo**:	Visualizar cursos ativos e excluir cursos<br>
**Atores**:	Administrador<br><br>



 Regras de negócio  	<br> 
**RN01**: O botão visualizar cursos deve estar ativo;<br>
**RN02**: Os cursos abertos devem ser listados em mosaico;<br>
**RN03**: O curso deve ter um link que ao clicar mostra seus dados;<br>
**RN04**: Ao clicar em excluir, deve aparecer mensagem para confirmar evento;<br>
**RN05**: Ao confirmar, o curso deverá sumir da página de cursos;<br><br><br>





CT02<br>
Funcionalidade: Visualizar e Excluir Cursos<br><br>

  Cenário: Visualizar cursos em mosaico<br>
    Dado que o usuário está na página de listar cursos<br>
    Quando ele acessar a página<br>
    Então ele deve ver os cursos distribuídos em mosaico<br>
    E cada curso deve exibir o nome, descrição, instrutor, data de início, data de término e status<br><br>

  Cenário: Excluir curso com confirmação<br>
    Dado que o administrador está na página de listar cursos<br>
    E há um curso disponível na lista<br>
    Quando ele clicar no botão de excluir do curso específico<br>
    Então o sistema deve exibir uma mensagem de confirmação<br>
    Quando ele confirmar a exclusão<br>
    Então o curso deve ser removido da lista de cursos<br>
    E o sistema deve exibir uma mensagem confirmando que o curso foi excluído com sucesso<br><br><br>

   >Durante o projeto fora utilizado a metodologia ágil com framework Scrum, sendo analisado artefatos por ordem de importância. Quanto aos testes, utilizei o método de teste funcional baseado nas partes críticas do sistema, focando no fluxo básico, fluxo alternativo e fluxo de exceção
