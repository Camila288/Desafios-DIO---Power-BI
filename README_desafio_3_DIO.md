### Passo a passo do desafio 3

- Criado um terminal dentro do Azure (Cloud Shell)
- Criar --> Banco de dados do Azure para MySQL, preenchi o nome do servidor (desafio-projeto-dio-c), nome (company) e senha na conta de adm, Segurança -> acesso público e depois criar. Deste modo há há criação da instância.
-  Foram criadas as tabelas e inseridos os dados no Power Shell pelo mysql -h desafio-projeto-dio-c.mysql.database.azure.com -u company -p e pegamos todos os códigos no github da Juliana.
-  Depois criamos a regra no Firewall na Azure para acesso ao banco de dados. Não houve muito trabalho quanto a isso.
- Houve a integração do Power BI com MySQL no Azure. Esta parte me deu bastante trabalho pois não foi explicitado na aula que eu precisava extrair o SSL e eu estava apenas baixando. Quando li a sequência de passos, consegui. Acredito que já tenha havido alguma atualização. Para isso, criamos uma conexão no MySQL, depois preenchemos connection name, username, use SSL,colocamos o download que fizemos do SSL já extraido dentro do MySQL, hostname (do Azure), e fizemos o test connection. 
- Transformação de dados: 
 Removi as tabelas desnecessárias;
Separei colunas com dados complexos (coluna address de employee);

Fiz as renomeações necessárias das tabelas.

Havia um valor nulo. Verifiquei as relações para tentar preencher a lacuna.

Modifiquei o valor monetário (tipo de dados -> número decimal fixo) na tabela employee.

Não havia departamento sem gerente e todos os colaboradores haviam gerentes.

Os colaboradores John Smith, Ramesh Narayan, Ahmad Jabbar e Alicia Zelaya estavam com uma alta quantidade de horas no projeto, o que pode indicar uma sobrecarga para alguns no trabalho.

Foram separadas as colunas address na tabela employee.

O primeiro mesclar consultas (employee_departament) foi feito com os campos Super_ssn da employee e Mgr_ssn da tabela departamento.
Foram removidas as colunas desnecessárias formadas.

Para a junção de colaboradores e respectivos nomes dos gerentes, eu utilizei o mesclar no Power BI. Desse modo, utilizei os campos Super_ssn da tabela employee com ela mesma, mudando o campo para Ssn. Removi as colunas desnecessárias posteriormente.

Mesclei as colunas de nome e sobrenome e renomeei para Employees.
Mesclei as consultas de departamento e localização e depois mesclei as colunas formadas e nomeei Store_location.

Neste caso utilizamos o mesclar para combinar valores de várias colunas em uma única, criando desse modo identificadores únicos. Caso tivéssemos utilizado o atribuir, o valor iria mudar com base em uma expressão ou condição. Essa operação é útil para padronizar dados, corrigir erros ou preparar dados para análise.

Foram agrupados os colaboradores por gente (Franklin Wong = 3, James Borg = 3, Jennifer Wallace = 2). 
