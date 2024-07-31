### Passo a passo do desafio 3

- Criado um terminal dentro do Azure (Cloud Shell)
- Criar --> Banco de dados do Azure para MySQL, preenchi o nome do servidor (desafio-projeto-dio-c), nome (company) e senha na conta de adm, Segurança -> acesso público e depois criar. Deste modo há criação da instância.
Image:

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/desafio_dio_image_1.png)

-  Foram criadas as tabelas e inseridos os dados no Power Shell pelo mysql -h desafio-projeto-dio-c.mysql.database.azure.com -u company -p e pegamos todos os códigos no github da Juliana.
-  Depois criamos a regra no Firewall na Azure para acesso ao banco de dados. Não houve muito trabalho quanto a isso.
- Conectamos ao MySQL na Azure utilizando o Wokbench. Esta parte me deu bastante trabalho pois não foi explicitado na aula que eu precisava converter o certificado do formado .crt para .pem e eu estava apenas baixando. Quando li a sequência de passos, consegui. Acredito que já tenha havido alguma atualização. Realizei a criação com uma conexão no MySQL, depois preenchi o connection name, username, use SSL,coloquei o download que foi feito do SSL já extraido dentro do MySQL, hostname (do Azure), e foi feito o test connection. 
![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/desafio_dio_image_2.png)

- Por fim, integrei o Power BI com MySQL na Azure.
![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/desafio_dio_image_3.png)

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

## Todas as tabelas estao nas imagens abaixo, respeitando todos os passos citados:

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/tabela_employee_final.png)

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/employee_2.png)


![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/employees_3.png)


![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/tabela_departament_final.png)

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/tabela_dept_location.png)

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/project.png)

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/tabela_dependent.png)

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/agrupamento_employees_per_manager.png)

![](https://github.com/Camila288/Desafios-DIO---Power-BI/blob/main/Images/works_on.png)

