# Projeto-3---Analise-de-risco-relativo
 Abaixo você encontrará toda a descrição e documentação de como esse porjeto foi feito: 
 *Hoje, dia 20/05 inicio no projeto 3, após apresentar o projeto dois e receber o feedback da Coach e das minhas colegas, mas antes de entrar mais afundo no projeto, pretendo organizar minhas metas semanais e administrar meu tempo sobre o projeto.*

*Tendo meus quadros de planejamento a minha frente, consigo dessa vez, visualizar melhor como atingir o que desejo. Estou focada e determinada em alcançar o marco 3 mas vamos com calma e perseverança para não haver mais obstáculos de tempo como no projeto anterior. Existem 28 sub objetivos, ao invés de separá-los apenas por marco, vou também trazer metas por semana. Creio que ficará mais claro ao visualizar as tabelas.*

[GERENCIAMENTO: PJ3](https://www.notion.so/GERENCIAMENTO-PJ3-76ac84a9ac69436a91effee5e20b3419?pvs=21)

# MARCO 1

## Processar e Preparar a Base de Dados

- 20/05
    
    Foquei no Job Preparation, agendei a mentoria tech, entreguei o perfil do GitHub e modifiquei meu currículo como indicado pela mentora na entrevista de RH.
    Agora, ás 23h50 fiz a organização e introdução do projeto, amanhã irei me aprofundar nos objetivos do mesmo.
    

- 21/05
    
    Hoje é o dia de iniciar o projeto com uma ideia mais completa do que é necessário fazer, afinal, é a mudança de sprint pela plataforma, então irei aproveitar esse momento para passar as tarefas dessa semana para o quadro físico no meu ambiente de estudos e também as tarefas que devo realizar no decorrer da semana.
    
    Talvez essa seja uma semana mais apertada em relação a tarefas, mas creio que posso trabalhar um pouco de cada vez e “desafogar” as tarefas.
    
    - [x]  Escrever e visualizar objetivos dessa semana
    - [x]  Me planejar para o evento da laboratoria do dia 06/06
    - [ ]  (Se possível) realizar desafio do job preparation
    - [x]  Job preparation: inbound - postar e movimentar mais conteudo relacionado as vagas que desejo.
    
    Hoje, durante a mudança de sprint, minha colega Bruna citou como poderia ser mais prático unir todas as tabelas antes mesmo de fazer a limpeza para agilizar esse processo e ter também uma maior visualização sobre as variáveis e concordo com ela, por isso, agora que já importei as tabelas, vou unir todas e ai começar a limpeza de uma só vez.
    
    Mas já adianto: diferente do projeto anterior, essas tabelas possuem uma quantidade diferente de linhas.
    
    **Informacoes_Usuario: 36.000**
    
    **Informacoes_Empres: 305.335 (agora se chama Historico Transações)**
    
    **Historico_Emprestim: 36.000 (agora se chama Informacoes Emprestimo)**
    
    **Classificacao_Inadimplencia: 36.000**
    
    Tendo esses números para visualização, creio que a antiga “informacoes de empréstimo” seja a única que não possa ser unida aqui, pois se trata de uma tabela de transações, como no primeiro projeto.
    
    Neste caso, pretendo unir apenas as tabelas com informações do usuário.
    
    Precisei modificar os nomes das tabelas pois não condizia com a informação fornecida.
    
    Agora, com os nomes corrigidos, posso uni-las.
    
    Unidas, então realizarei uma pausa e retorno em breve. (19h40)
    
    retorno(22:30)
    
    Como fui para a academia e ficou muito tarde para retornar, vou preferir dedicar um tempo amanhã (a mais) do que me privar o sono novamente.
    
- O objetivo do projeto
    
    “O objetivo da análise é desenvolver um score de crédito a partir de uma análise de dados e avaliação do risco relativo que possa classificar os solicitantes em diferentes categorias de risco com base em sua probabilidade de inadimplência. Essa classificação permitirá ao banco tomar decisões informadas sobre quem conceder crédito, reduzindo assim o risco de empréstimos não reembolsáveis. Além disso, a integração da métrica existente de pagamentos em atraso fortalecerá a capacidade do modelo de identificar riscos, contribuindo assim para a solidez financeira e eficiência operacional do banco.”
    
- Sobre o Projeto
    
    Este é um projeto que planeja trazer um avanço em nossa análise de dados, por tanto, as ferramentas utilizadas serão:
    
    - BigQuery
    - Colab
    - Looker studios
    - Google apresentações
    
    Linguagens:
    
    - SQL
    - Phyton
    
    | Arquivo | Variável | Descrição |
    | --- | --- | --- |
    | user_info | user id | Número de identificação do cliente (único para cada cliente) |
    |  | age | Idade do cliente |
    |  | sex | Gênero do cliente |
    |  | last month salary | Último salário mensal que o cliente informou ao banco |
    |  | number dependents | Número de dependentes |
    | loans_outstanding | loan id | Número de identificação do empréstimo (único para cada empréstimo) |
    |  | user id | Número de identificação do cliente |
    |  | loan type | Tipo de empréstimo (real state = imóveis, others= outros) |
    | loans_detail | user id | Número de identificação do cliente |
    |  | more 90 days overdue | Número de vezes que o cliente apresentou atraso superior a 90 dias |
    |  | using lines not secured personal assets | Quanto o cliente está utilizando em relação ao seu limite de 
    crédito, em linhas que não são garantidas por bens pessoais, como 
    imóveis e automóveis |
    |  | number times delayed payment loan 30 59 days | Número de vezes que o cliente atrasou o pagamento de um empréstimo (entre 30 e 59 dias) |
    |  | debt ratio | Relação entre dívidas e ativos do cliente. Taxa de endividamento = Dívidas / Patrimonio |
    |  | number times delayed payment loan 60 89 days | Número de vezes que o cliente atrasou o pagamento de um empréstimo (entre 60 e 89 dias) |
    | default | user id | Número de identificação do cliente |
    |  | default flag | Classificação dos clientes inadimplentes (1 para clientes já 
    registrados alguma vez como inadimplentes, 0 para clientes sem histórico
     de inadimplência) |
    
    > “Nesta fase inicial, o cálculo do risco relativo de cada variável é essencial para estabelecer uma base sólida sobre a qual construiremos a pontuação/score de crédito em marcos subsequentes. Sua análise neste marco estabelecerá as bases para uma avaliação de crédito mais precisa e automatizada que acabará contribuindo para a robustez financeira e operacional do banco.
    > 
    > 
    > No final deste marco, espera-se que você apresente suas descobertas e o cálculo do risco relativo associado a cada variável de forma clara e concisa, junto com quaisquer percepções adicionais que você descobriu. Este é um passo crucial na sua jornada rumo à criação de um sistema de análise de crédito automatizado e preciso.”
    > 
    
- FORMULA RENOMEAR TABELA
    
    
    ```
    CREATE TABLE
      local-parsec-424021-r9.dataset_banco.Informacoes_Emprestimos
       AS
         SELECT
           *
           FROM `local-parsec-424021-r9.dataset_banco.Historico_Emprestimo`
    ```
    
    ```
    DROP TABLE
    `local-parsec-424021-r9.dataset_banco.Historico_Emprestimo`
    ```
    
- FORMULA UNIR TABELAS
    
    
    ```
    CREATE OR REPLACE TABLE
      `dataset_banco.Informacoes_Usuario`
        AS
         SELECT
         T1.*,
         T2.more_90_days_overdue,
         T2.using_lines_not_secured_personal_assets,
         T2.number_times_delayed_payment_loan_30_59_days,
         T2.debt_ratio,
         T2.number_times_delayed_payment_loan_60_89_days,
    
        FROM `dataset_banco.Informacoes_Usuario` AS T1
    
        JOIN `dataset_banco.Informacoes_Emprestimos` AS T2
    
        ON T1.user_id=T2.user_id
    
    ```
    
    <aside>
    🛠 É possível unir mais de duas tabelas por vez utilizando LEFT JOIN, porém, ainda na conversa de hoje, ouvi das minhas colegas que essa fórmula pode ignorar algumas informações das variáveis fazendo com que você as perca, então, achei mais cuidadoso unir uma por vez, tendo em vista que já estou agilizando o processo, mas o foco é entregar um bom trabalho e compreender as ferramentas, não entregar rápido.
    
    </aside>
    
    ```
    CREATE OR REPLACE TABLE
      `dataset_banco.Informacoes_Usuario`
        AS
         SELECT
         T1.*,
         T2.default_flag,
    
        FROM `dataset_banco.Informacoes_Usuario` AS T1
    
        JOIN `dataset_banco.Classificacao_Inadimplencia` AS T2
    
        ON T1.user_id=T2.user_id
    ```
    

- 22/05
    
    Hoje temos um tempo na agenda onde não ha nenhuma oficina, então estou utilizando esse tempo para trabalhar no projeto.
    
    Acabei de encontrar valores nulos e apesar da indicação da LAB, também tive o mesmo raciocínio: os valores nulos, nas colunas last_month_salary e number_dependents não podem simplesmente serem excluídos por a existência deles nos ajudará na correlação de algumas variáveis depois.
    
    Para fins de conhecimento:
    
    ![Captura de Tela (46).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/912b9aab-79b0-470b-a2a4-4fb6d376c76e/5f73a428-e89b-4c2b-ba0d-ab2d0b0b7ed2.png)
    
    Busquei por duplicados também, mas nenhuma informação duplicada.
    
    Agora vou analisar os dados fora do escopo através da correlação entre as variáveis. Decidi fazer correlação de uma variável para quase todas as outras, veja mais em “FORMULA CORRELAÇAO”.
    
    last_mouth_salary, apesar de ter uma correlação maior com number_dependents, não ter valores significativos o suficiente para precisar escolher entre ela e outra variável na busca por respostas. A correlação entre as duas é de 0,077… sendo a maior dentre as correlações.
    
    Mas, calculando, entrei alta correlação entre 3 variáveis:
    
     more_90_days_overdue entre number_times_delayed_payment_loan_30_59_days (~0,98) e number_times_delayed_payment_loan_60_89_days (~0,99)
    
    Por isso, decidi calcular o desvio padrão, como indicado nos documentos da LAB e a com maior desvio, será mantida.
    
    Ao calcular o desvio, meu palpite foi confirmado: number_times_delayed_payment_loan_30_59_days deve ser mantida pois possui um desvio maior.
    
    ![Captura de Tela (61).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/939467c8-11fd-454d-b157-aee855486d2d/ca6b1200-6ed2-41d5-977a-ad4485aa0934.png)
    
    Antes der utilizar fazer a exclusão da variável “6089”, vou padronizar as variáveis categóricas e numéricas, então utilizei UPPER. Após isso, substituí OTHER para OTHERS; eu iria utilizar UPDATE, mas descobri que essa função não está disponível na versão gratuita haha, mas existe outra opção para isso, vide FORMULA CASE WHEN.
    
    Agora que padronizei as tabelas, posso excluir a variável que não desejo manter.
    
- FORMULA CONTAGEM NULOS
    
    ```
    SELECT
      COUNTIF (user_id IS NULL) AS user_id_nulos,
      COUNTIF (age IS NULL) AS age_nulos,
      COUNTIF (sex IS NULL) AS sex_nulos,
      COUNTIF (last_month_salary IS NULL) AS last_month_salaryd_nulos,
      COUNTIF (number_dependents IS NULL) AS number_dependents_nulos,
      COUNTIF (more_90_days_overdue IS NULL) AS more_90_days_overdue_nulos,
      COUNTIF (using_lines_not_secured_personal_assets IS NULL) AS using_lines_not_secured_personal_assets_nulos,
      COUNTIF (number_times_delayed_payment_loan_30_59_days IS NULL) AS number_times_delayed_payment_loan_30_59_days_nulos,
      COUNTIF (debt_ratio IS NULL) AS debt_ratio_nulos,
      COUNTIF (number_times_delayed_payment_loan_60_89_days IS NULL) AS number_times_delayed_payment_loan_60_89_days_nulos,
      COUNTIF (default_flag IS NULL) AS default_flag_nulos
      FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
- FORMULA CONTAGEM DUPLICADOS
    
    
    ```
    SELECT
      age,
      sex,
      last_month_salary,
      number_dependents,
      more_90_days_overdue,
      using_lines_not_secured_personal_assets,
      number_times_delayed_payment_loan_30_59_days,
      debt_ratio,
      number_times_delayed_payment_loan_60_89_days,
      default_flag,
        COUNT (*) AS quantidade
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    
    GROUP BY
      age,
      sex,
      last_month_salary,
      number_dependents,
      more_90_days_overdue,
      using_lines_not_secured_personal_assets,
      number_times_delayed_payment_loan_30_59_days,
      debt_ratio,
      number_times_delayed_payment_loan_60_89_days,
      default_flag
        HAVING
          COUNT(*) >1;
          
    ```
    
    Repare que não incluí a coluna user_id pois no projeto anterior, tive uma breve dificuldade em encontrar duplicados pois o BigQuery faz uma busca com base em todas as informações da linha, no caso, usa a primeira coluna como referência. Se tivesse o mesmo caso de IDs não duplicados, mas nomes repetidos, eu não conseguiria encontrar o que procuro, mas excluindo id da busca isso se torna possível, por exemplo:
    
    ID                           NOME
    
    3455                       Carlos de Andrade
    
    7469                       Carlos de Andrade 
    
    Para evitar esse tipo de duplicados, exclui essa coluna da busca, mas como não encontrei nenhuma informação desse tipo (não possuímos o nome dos clientes), realizei outra busca com a coluna user_id e dessa vez, nenhum duplicado.
    
- FORMULA CORRELAÇÃO
    
    
    ```
    SELECT
      CORR(last_month_salary, number_dependents) AS corre_lastms_numberd,
      CORR(last_month_salary, more_90_days_overdue) AS corre_lastms_m90daysover,
      CORR(last_month_salary, using_lines_not_secured_personal_assets) AS corre_lastms_ulnotspersass,
      CORR(last_month_salary, number_times_delayed_payment_loan_30_59_days) AS corre_lastms_numbtdelpayloan3059,
      CORR(last_month_salary, debt_ratio) AS corre_lastms_dabratio,
      CORR(last_month_salary, number_times_delayed_payment_loan_60_89_days) AS corre_lastms_numbtdelpay6089,
      CORR(last_month_salary, default_flag) AS corre_lastms_defaultflag
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Nesta fórmula, eu calculo a correlação entre a coluna last_month_salary e as outras colunas a partir de number_dependents; abaixo, o resultado de cada uma respectivamente:
    
    ![Captura de Tela (47).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/351b7cb4-0a68-41ff-98bc-5c5c45f639ca/8315f89e-5510-415e-ae7a-d50ac3309672.png)
    
    ![Captura de Tela (49).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/0ebfc440-418a-4ee4-9d1b-d3450d7d6082/02921ee5-134a-4e1f-af80-58fd13805001.png)
    
    ![Captura de Tela (48).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/10840716-29b6-48cc-bdd8-d31600d1cc51/91422eb5-09df-402e-9ec5-89a4e5250a41.png)
    
    Agora, o mesmo com a variável number_dependents:
    
    ```
    SELECT
      CORR(number_dependents, more_90_days_overdue) AS corr_numberd_m90daysover,
      CORR(number_dependents, using_lines_not_secured_personal_assets) AS corr_numberd_ulnotspersass,
      CORR(number_dependents, number_times_delayed_payment_loan_30_59_days) AS corr_numberd_numbtdelpayloan3059,
      CORR(number_dependents, debt_ratio) AS corr_numberd_dabratio,
      CORR(number_dependents, number_times_delayed_payment_loan_60_89_days) AS corr_numberd_numbtdelpay6089,
      CORR(number_dependents, default_flag) AS corr_numberd_defaultflag
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Resultados:
    
    ![Captura de Tela (50).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/18e9635a-7ab4-452f-bdac-a1c1f3a1a12a/a9701993-d9d8-4148-8f9a-5550b54b8849.png)
    
    ![Captura de Tela (51).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/f8b7534b-a7b2-4ff0-b16e-ab33a3c125f1/25e38ba3-fca7-4f56-8739-abf80c81cd79.png)
    
    ![Captura de Tela (52).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/a643dfee-a502-45fa-98e9-96b323e88205/9f6a2459-6a65-4f5a-a769-2ef5d994de91.png)
    
    Novamente, não há uma correlação alta entre essa variável e as demais, porém… ao correlacionar a próxima variável:
    
    ```
    SELECT
      CORR(more_90_days_overdue, using_lines_not_secured_personal_assets) AS corr_m90daysover_ulnotspersass,
      CORR(more_90_days_overdue, number_times_delayed_payment_loan_30_59_days) AS corr_m90daysover_numbtdelpayloan3059,
      CORR(more_90_days_overdue, debt_ratio) AS corr_m90daysover_dabratio,
      CORR(more_90_days_overdue, number_times_delayed_payment_loan_60_89_days) AS corr_m90daysover_numbtdelpay6089,
      CORR(more_90_days_overdue, default_flag) AS corr_m90daysover_defaultflag
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Resultados:
    
    ![Captura de Tela (53).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/2cbc3bcb-8b3a-4dd6-b7e6-a7cb75a5d5a7/9dcdddce-ae24-4b84-9c19-4a23f824f79d.png)
    
    ![Captura de Tela (54).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/323c83a9-a1f9-4ba4-a0e2-cfa8a56e4f16/19ffe461-882a-49e7-8991-5f5d03b8c982.png)
    
    Vemos que, a variável more_90_days_overdue tem um alta correlação positiva entre as variáveis umber_times_delayed_payment_loan_30_59_days (~0,98) e number_times_delayed_payment_loan_60_89_days (~0,99) isso porque, a variável de comparação se trata de uma coluna referente a um atraso de mais de 90 dias nos pagamentos, as seguintes mostram as porções menores desses atrasos.
    
    Sabendo que uma correlação positiva indica uma crescente em ambas, a tendência é que quem tem um histórico de atrasar 30 dias, tende a atrasar mais de 90 dias, logo, podemos descartar uma dessas variáveis, mas vamos continuar coma correlação e em seguida ver o desvio padrão de ambas.
    
    ```
    SELECT
      CORR(using_lines_not_secured_personal_assets, number_times_delayed_payment_loan_30_59_days) AS corr_ulnotspersass_numbtdelpayloan3059,
      CORR(using_lines_not_secured_personal_assets, debt_ratio) AS corr_ulnotspersass_dabratio,
      CORR(using_lines_not_secured_personal_assets, number_times_delayed_payment_loan_60_89_days) AS corr_ulnotspersass_numbtdelpay6089,
      CORR(using_lines_not_secured_personal_assets, default_flag) AS corr_ulnotspersass_defaultflag
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    
    ```
    
    Resultados:
    
    ![Captura de Tela (55).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/83911728-bfcd-401a-b155-85b7e83bafc4/d5be582e-79e6-44a3-b58d-57292fbe8ec1.png)
    
    ![Captura de Tela (56).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/c76ed768-01ce-4967-95a8-5a0a85d3bcb6/e4596ca2-759e-46dc-9ac3-de1442a1f200.png)
    
    Índice de correlação baixíssimo.
    
    ```
    SELECT
      CORR(number_times_delayed_payment_loan_30_59_days, debt_ratio) AS corr_numbtdelpayloan3059_dabratio,
      CORR(number_times_delayed_payment_loan_30_59_days, number_times_delayed_payment_loan_60_89_days) AS corr_numbtdelpayloan3059_numbtdelpay6089,
      CORR(number_times_delayed_payment_loan_30_59_days, default_flag) AS corr_numbtdelpayloan3059_defaultflag
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Resultados:
    
    ![Captura de Tela (57).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/ae089ab2-e81c-44e3-be07-1377b537e475/479bc8c5-2e06-4595-badd-f4267c6c98b7.png)
    
    Novamente, correlação alta entre number_times_delayed_payment_loan_30_59_days e number_times_delayed_payment_loan_60_89_days.
    
    ```
    SELECT
      CORR(debt_ratio, number_times_delayed_payment_loan_60_89_days) AS corr_dabratio_numbtdelpaydebt_ratio6089,
      CORR(debt_ratio, default_flag) AS corr_dabratio_defaultflag
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Resultados:
    
    ![Captura de Tela (58).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/536d09a9-0e9c-43ea-a650-f1d15ee32078/b2a96f22-297e-4b34-babf-3f4181036d1f.png)
    
    Baixa correlação.
    
    ```
    SELECT
      CORR(number_times_delayed_payment_loan_60_89_days, default_flag) AS corr_numbtdelpaydebt_ratio6089_defaultflag
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    
    ```
    
    Resultados:
    
    ![Captura de Tela (59).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/c3a19d25-c1c5-492a-8195-4b55e28fb261/c63b9b7a-0068-4cfb-9879-1f328bed7572.png)
    
    Baixa correlação.
    
- FORMULA DESVIO PADRÃO  (AMOSTRA)
    
    ```
    SELECT
      STDDEV_SAMP(number_times_delayed_payment_loan_30_59_days) AS desvio_3059,
      STDDEV_SAMP(number_times_delayed_payment_loan_60_89_days) AS desvio_6089
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    
    ```
    
- FORMULA UPPER
    
    ```
    CREATE OR REPLACE TABLE 
     `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
        AS
          SELECT
          user_id,
          loan_id,
          UPPER (loan_type) AS loan_type_upper
    FROM `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
    ```
    
- FORMULA CASE WHEN
    
    
    Primeira tentativa (paga):
    
    ```sql
    UPDATE `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
    SET loan_type_upper = CASE
                       WHEN (loan_type_upper) = 'OTHER' THEN 'OTHERS'
                       ELSE loan_type_upper
                    END
    WHERE LOWER(loan_type_upper) = 'OTHER';
    ```
    
    A formula que usei (gratuita):
    
    ```
    SELECT
      user_id,
      loan_id,
      CASE
        WHEN (loan_type_upper) = 'OTHER' THEN 'OTHERS'
                              ELSE loan_type_upper
                                END AS loan_type_upper
        FROM `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
    ```
    
    Agora que foi testada e deu certo, posso acrescentar CREATE OR REPLACE TABLE.
    
    ```
    CREATE OR REPLACE TABLE
    `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
      AS
        SELECT
        user_id,
        loan_id,
        CASE
          WHEN (loan_type_upper) = 'OTHER' THEN 'OTHERS'
                              ELSE loan_type_upper
                                END AS loan_type_upper
        FROM `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
    ```
    
- FORMULA MODIFICAÇÃO TABELA informacoes_usuario
    
    ```
    CREATE OR REPLACE TABLE
    `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
      AS
       SELECT
         user_id,
         age,
         sex,
         last_month_salary,
         number_dependents,
         number_times_delayed_payment_loan_30_59_days,
         more_90_days_overdue,
         using_lines_not_secured_personal_assets,
         debt_ratio,
         default_flag
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    

- 23/05
    
    Estou agora (13:00) identificando e gerindo dados discrepantes em variáveis numéricas, a.k.a. encontrando e tratando outliers em 3 variáveis onde creio que eles serão encontrados: last_month_salary, using_lines_not_secured_personal_assets e debt_ratio.
    
    Utilizando AVG, MAX e MIN consegui encontrar os extremos de cada variável, assim, creio que consigo determinar um limite de valores…
    
    Devido os valores encontrados e também a natureza da tabela, creio que excluir outliers n seja uma boa, então decidi transforma-los.
    
    Gostei de como a coluna ficou apresentada com os valores substituídos, então vou modifica-la oficialmente.
    
    Agora(14:31) terminei a gestão de outliers, vou fazer uma pausa e mais tarde se possível, adiantar a próxima tarefa.
    
- FORMULA AVG, MAX E MIN PARA OUTLIERS
    
    
    ```jsx
    SELECT
      AVG(last_month_salary),
      MAX(last_month_salary),
      MIN(last_month_salary),
      
      AVG(using_lines_not_secured_personal_assets),
      MAX(using_lines_not_secured_personal_assets),
      MIN(using_lines_not_secured_personal_assets),
      
      AVG(debt_ratio),
      MAX(debt_ratio),
      MIN(debt_ratio)
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Resultados para last_month_salary:
    
    ![Captura de Tela (62).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/2176f362-5ff1-43da-83e5-a01e700bbf0c/c2a1e13c-ffcd-40c5-a636-1d0c5f61835e.png)
    
    Resultados para using_lines_not_secured_personal_assets:
    
    ![Captura de Tela (63).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/e9088ff8-8edb-44fd-9170-bbb5a21bac6c/64618c25-e105-42a8-8a9e-bcf24987e8cb.png)
    
    Resultados para debt_ratio:
    
    ![Captura de Tela (64).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/bf3ceded-b9ff-4cb3-adde-5c48ee9959c7/4aa1412b-e3b5-4868-8807-613ed9ac5918.png)
    
- FORMULA TRANSFORMAR OUTLIERS
    
    
    ```jsx
    SELECT
      IF (last_month_salary >20000 OR last_month_salary <1000, AVG(last_month_salary) OVER(), last_month_salary) AS last_month_salary_media
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Nesta fórmula, estou pedindo para que o  BQ substitua valores maiores que 10000 e menores que 1000 pela media da coluna last_month_salary e ainda estou modificando o nome para “last_month_salary_media”.
    
    Para a segunda variável:
    
    ```
    SELECT
      IF (using_lines_not_secured_personal_assets >7 OR using_lines_not_secured_personal_assets <0.5, AVG(using_lines_not_secured_personal_assets) OVER(), using_lines_not_secured_personal_assets) AS using_lines_not_secured_personal_assets_media
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Para a terceira:
    
    ```
    
    SELECT
      IF (debt_ratio >2000 OR debt_ratio <10, AVG(debt_ratio) OVER(), debt_ratio) AS debt_ratio_media
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
- FORMULA MODIFY TABELA OUTLIERS
    
    ```
    CREATE OR REPLACE TABLE
    `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
      AS
       SELECT
       user_id,
       age,
       sex,
       IF (last_month_salary >20000 OR last_month_salary <1000, AVG(last_month_salary) OVER(), last_month_salary) AS last_month_salary_media,
       number_dependents,
       number_times_delayed_payment_loan_30_59_days,
       more_90_days_overdue,
       IF (using_lines_not_secured_personal_assets >7 OR using_lines_not_secured_personal_assets <0.5, AVG(using_lines_not_secured_personal_assets) OVER(), using_lines_not_secured_personal_assets) AS using_lines_not_secured_personal_assets_media,
         IF (debt_ratio >2000 OR debt_ratio <10, AVG(debt_ratio) OVER(), debt_ratio) AS debt_ratio_media,
         default_flag
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    

*Obs. para mim: Parabéns! você terminou as metas dessa semana! Fico feliz que nosso planejamento deu certo :)* 

*Mas para que a gente não se perca no futuro (provavelmente no domingo haha) aqui vai um breve resumo do que iríamos fazer hoje se não estivéssemos morrendo de sono:*

- *Terminamos nos outliers porém, apesar da fórmula dar certo, acredito que possa existir uma forma mais organizada de determinar os limites e valores nas 3 variáveis que calculamos ou ao menos podemos tentar a fórmula que Ester encaminhou no grupo do slack utilizando quartis para estipular esses valores e tratar as variáveis. Acredito que a média pode ser uma saída, mas me parece que seguir com ela pode fornecer uma análise não tão apurada quando podemos ter com quartis, mas… é uma tentativa, caso não tenho muita diferença, podemos decidir qual caminho seguir, mas acredito que faça sim haha*
- *Estamos indo para criar novas variáveis e modificar dados, acho que pode ser legal ter mais uma variável de texto com base naquela classificação de risco já existente na tabela.*

 *É isto Brenda do futuro, boa noite e bom descanso hehe!*

!https://media1.giphy.com/media/PEqSiRCitokww/giphy.gif?cid=7941fdc6vjbe0v3mry9q4qk9slannofgxdyjcdtor443co50&ep=v1_gifs_search&rid=giphy.gif&ct=g

- 26/05
    
    Hoje é domingo e o resto do ditado você já conhece hehe… mas para hoje, vamos corrigir alguns valores como citei anteriormente que planejava fazer, porém, para se mais prático, já que terei de correlatar as variáveis que irei criar após adiciona-las na tabela, antes, vou cria-las e ao adicionar, consigo partir para o tratamento da tabela, removendo as médias que fiz anteriormente e colocando as novas com  base nos quartis.
    
    A ideia sugerida no projeto é criar uma coluna com os totais de empréstimo por cliente, então irei focar nessa coluna primeiro e caso surja uma nova que possa ser útil, irei acrescenta-la.
    
    Para adicionar a nova variável precisei criar outra tabela com os totais.
    
    Como vou corrigir os valores de 3 variaveis, terei de excluir as que criei e unir novamente para depois modifica-las, apenas para last_month_salary terei de trazer outra vez a tabela de informação.
    
- FORMULA NOVA VARIAVEL DISTINCT
    
    ```
    SELECT
      user_id, COUNT (distinct_valor) AS Total_emprestimo
        FROM (
          SELECT DISTINCT user_id, loan_id AS distinct_valor
            FROM `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
        ) AS sub
        GROUP BY user_id
    ```
    
    Caso eu quisesse somar valores, bastava substituir COUNT por SUM.
    
- FORMULA CORREÇÃO OUTLIERS QUARTILES
    
    O Chat GPT indicou uma fórmula gigantesca que cria diversas variáveis calculando quartis e mediana e eu sinceramente achei gigantesca e não sei se como acrescimo numa tabela ela iria funcionar, mas, talvez, como uma tabela auxiliar ela ajude… porém, acredito que para lidar com outliers, existem maneiras mais práticas e diretas.
    
    ```
    WITH stats AS (
     SELECT
        APPROX_QUANTILES(using_lines_not_secured_personal_assets_media, 2)[OFFSET(1)] AS median
      FROM
       `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ),
    filtered_data AS (
      SELECT
        *,
        IF(using_lines_not_secured_personal_assets_media < Q1 - 1.5 * (Q3 - Q1) OR using_lines_not_secured_personal_assets_media > Q3 + 1.5 * (Q3 - Q1), median, using_lines_not_secured_personal_assets_media) AS valor_corrigido
      FROM
        `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`,
        (SELECT
           APPROX_QUANTILES(using_lines_not_secured_personal_assets_media, 4)[OFFSET(1)] AS Q1,
           APPROX_QUANTILES(using_lines_not_secured_personal_assets_media, 4)[OFFSET(3)] AS Q3
         FROM
           `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`) stats,
        (SELECT
           APPROX_QUANTILES(using_lines_not_secured_personal_assets_media, 2)[OFFSET(1)] AS median
         FROM
           `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`) mediana
    )
    SELECT
      *
    FROM
      filtered_data;
    ```
    
    Fiz a divisão básica de quartis e agora, creio que posso utilizar aquela formula de modificação com os limites mais assertivos.
    
    ```jsx
    WITH data AS (
      SELECT
        last_month_salary_media
      FROM
        `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    )
    SELECT
      APPROX_QUANTILES(last_month_salary_media, 4) AS quartis
    FROM
      data 
    ```
    
    RESULTADOS:
    
    ![Captura de Tela (66).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/fe5c9d38-c509-4971-be2e-27ec77e41477/07e7921e-1934-47a6-ad54-0d6419e142cd.png)
    
    ```
    WITH data AS (
      SELECT
        using_lines_not_secured_personal_assets_media
      FROM
        `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    )
    SELECT
      APPROX_QUANTILES(using_lines_not_secured_personal_assets_media, 4) AS quartis
    FROM
      data 
    ```
    
    RESULTADOS:
    
    ![Captura de Tela (65).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/c5c322ae-45ac-479b-9748-79a068119702/ed541c30-71a0-45a8-ba85-ce09be5cd04d.png)
    
    ```
    WITH data AS (
      SELECT
        debt_ratio_media
      FROM
        `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    )
    SELECT
      APPROX_QUANTILES(debt_ratio_media, 4) AS quartis
    FROM
      data 
    ```
    
    RESULTADOS:
    
    ![Captura de Tela (67).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/00af34e3-77e9-498f-9f4f-e46ae84070ef/204d3f4a-c982-459e-8462-6d4d549484e5.png)
    
- FORMULA TABELA ADICIONAL TOTAL EMPRESTIMOS
    
    ```
    CREATE TABLE local-parsec-424021-r9.dataset_banco.Total_Emprestimos_Clientes
      AS
        SELECT
         user_id, COUNT (distinct_valor) AS Total_emprestimo
        FROM (
          SELECT DISTINCT user_id, loan_id AS distinct_valor
            FROM `local-parsec-424021-r9.dataset_banco.Historico_transacoes`
        ) AS sub
        GROUP BY user_id
    ```
    
- QUARTILES CORRIGIDO
    
    Eu não sei… mas, ao meu ver, deu o mesmo valor… então tava certo haha.
    
    ```
    SELECT
      user_id,
      age,
      sex,
        IF (last_month_salary >20000 OR last_month_salary <1000, AVG(last_month_salary) OVER(), last_month_salary) AS last_month_salary_media,
      number_dependents,
      number_times_delayed_payment_loan_30_59_days,
      more_90_days_overdue,
      IF (using_lines_not_secured_personal_assets >7 OR using_lines_not_secured_personal_assets <0.5, AVG(using_lines_not_secured_personal_assets) OVER(), using_lines_not_secured_personal_assets) AS using_lines_not_secured_personal_assets_media,
      IF (debt_ratio >2000 OR debt_ratio <10, AVG(debt_ratio) OVER(), debt_ratio) AS debt_ratio_media,
      default_flag
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
- SEGUNDA UNIAO DE TABELAS
    
    ```
    CREATE OR REPLACE TABLE `dataset_banco.Informacoes_Usuario`
    AS
    SELECT
    T1.user_id,
    T1.age,
    T1.sex,
    T1.number_dependents,
    T1.last_month_salary_media,
    T1.Total_emprestimo,
    T2.loan_type_upper,
    T1.debt_ratio_media,
    T1.number_times_delayed_payment_loan_30_59_days,
    T1.more_90_days_overdue,
    T1.using_lines_not_secured_personal_assets_media,
    T1.default_flag
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario` AS T1
    
    JOIN `dataset_banco.Historico_transacoes` AS T2
    
    ON T1.user_id=T2.user_id
    ```
    
- ORGANIZAÇAO DE TABELA E ACRESCIMO DE VARIAVEL
    
    ```
    CREATE OR REPLACE TABLE `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    AS
    SELECT
      *,
      CASE
        WHEN default_flag = 0 THEN "SEM RISCO"
        WHEN default_flag = 1 THEN "RISCO INADIMPLENCIA"
        ELSE "NULO"
      END AS default_flag_name
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
- REORGANIZAÇAO INT64
    
    ```
    CREATE OR REPLACE TABLE `dataset_banco.Informacoes_Usuario` AS 
    SELECT
    user_id,
    age,
    sex,
    number_dependents,
    CAST(last_month_salary_media AS INT64) AS last_month_salary_media,
    Total_emprestimo,
    loan_type_upper,
    CAST(debt_ratio_media AS INT64) AS debt_ratio_media,
    number_times_delayed_payment_loan_30_59_days,
    more_90_days_overdue,
    CAST(using_lines_not_secured_personal_assets_media AS INT64) AS using_lines_not_secured_personal_assets_media,
    default_flag,
    default_flag_name
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
- REORGANIZACAO CASE WHEN
    
    ```
    CREATE OR REPLACE TABLE `dataset_banco.Informacoes_Usuario`
    AS
    SELECT
    user_id,
    age,
    CASE 
      WHEN (sex)= 'F' THEN 'FEMININE'
      WHEN (sex)= 'M' THEN 'MASCULINE'
      ELSE sex
      END AS sex,
    number_dependents,
    last_month_salary_media,
    Total_emprestimo,
    loan_type_upper,
    debt_ratio_media,
    number_times_delayed_payment_loan_30_59_days,
    more_90_days_overdue,
    using_lines_not_secured_personal_assets_media,
    default_flag,
    default_flag_name
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    

*Essa foi uma semana revigorante onde consegui implementar com êxito a minha técnica visual de organização, então estou muito feliz.*

*É domingo e sem nenhuma dor de cabeça, pela primeira vez eu consegui vir num fim de semana e trabalhar no projeto, mesmo após um dia de trabalho, mesmo após passar a semana focada nisso e em  outros afazeres, mesmo tendo buscado novas coisas que eu ainda não havia trabalhado em SQL.* 

*Cito tudo isso pois esse foi o meu maior desafio no projeto  anterior e eu percebi que sou muito competitiva e amo vencer desafios, por isso, utilizei da minha percepção dos erros passados para corrigir e melhorar meu desempenho! Me deixa extremamente animada perceber o quanto consigo me desenvolver quando observo e dou valor ao meu processo de aprendizagem; mas não posso esquecer do quanto tem sido maravilhoso ter uma rede de apoio que me lembra sempre o quanto tenho trabalhado duro e estou atingindo meus objetivos… serei eternamente grata a quem me fez olhar com carinho para o meu desenvolvimento.*

*Por fim, estou finalizando essa etapa do projeto antes do previsto, amanhã iniciarei a análise exploratória.*

*Até lá!*

!https://media0.giphy.com/media/0MtsZT6xJKsJ6ENzDq/giphy.gif?cid=7941fdc6htuvkwpsac4zq4auomzh6au4plk6xrgfo94j1z02&ep=v1_gifs_search&rid=giphy.gif&ct=g

---

## Fazer uma Análise Exploratória

- 27/05
    
    Apesar de ontem eu ter finalizado os objetivos dessa primeira parte, agora, durante a aprendizagem colaborativa, percebi que não havia tratado os valores nulos que surgiram :v 
    
    então vou corrigir esses dados antes de ir para a segunda parte.
    
    Confesso que hoje estou um pouquinho cansada :’) mas ao menos consegui entrar no looker studio e montar alguns gráficos, para variáveis numéricas e para variáveis categóricas. apliquei medidas de tendência central(media e mediana) para ver a distribuição em algumas variáveis, no caso, nas que tratei os outliers para ver como estava e percebi que tive êxito até então… agora, basta continuar analisando as outras variáveis para ver o que posso encontrar e explorar um pouco mais o looker, mas até então creio que esteja indo bem :) 
    
    ![Captura de Tela (72).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/8500c24f-90b3-4f93-9f7a-24b340a180fb/Captura_de_Tela_(72).png)
    
    ![Captura de Tela (69).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/3ab0e778-0844-46d7-85d0-4e5b3492d2fe/Captura_de_Tela_(69).png)
    
    ![Captura de Tela (68).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/07f550f3-2309-4351-bcd6-2abe150bd738/Captura_de_Tela_(68).png)
    
- CORRECAO/SUBSTITUICAO NULOS
    
    ```
    CREATE OR REPLACE TABLE `dataset_banco.Informacoes_Usuario`
    AS 
    SELECT
      user_id,
      age,
      sex,
      IFNULL (number_dependents, 0) AS number_dependents_mod,
      CAST(IFNULL (last_month_salary_media, AVG(last_month_salary_media) OVER())AS INT64) AS last_month_salary_media_mod,
      Total_emprestimo,
      loan_type_upper,
      debt_ratio_media,
      number_times_delayed_payment_loan_30_59_days,
      more_90_days_overdue,
      using_lines_not_secured_personal_assets_media,
      default_flag,
      default_flag_name
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    

- 29/05
    
    Infelizmente no dia 28/05 eu não estava muito bem, muita fadiga, ansiosa e mal consegui dormir corretamente, mas não tem problema… Agora são 00:45 e estou pelo menos analisando e administrando os próximos passos do projeto.
    
    Pelo que vi, antes de criar um bloxpot terei de calcular os quartis no bigquery, creio que caso não consiga, posso pedir ajuda para as meninas amanhã (hoje mais tarde).
    

- 30/05
    
    Essa foi uma semana corrida e infelizmente não pude focar como gostaria ou pelo tempo que gostaria no projeto, então acabei “travando” na visualização da distribuição.
    
    Mas aproveitando que amanhã (sexta) estarei em casa, consigo utilizar o tempo que não pude ontem (quarta) devido o trabalho, hoje e amanhã 🙂
    
    Meu plano é calcular quartis de variáveis numéricas que julgo serem importantes para classificar os perfis de clientes encontrados no banco.
    
    Estou lidando com uma situação bem chata aqui… pensei que utilizar a média havia sido um problema nos cálculos, mas fui analisar os números dos empréstimos e realmente existem números mt extremos, dificilmente um intermediário. Ou o cliente atrasa até 10 dias para pagar ou ele não paga dentro de 100 dias. Peculiar, mas acho que isso pode acontecer, agora preciso entender como vou lidar com esse fato. 
    
    Já calculei quartis, calculei correlação entre as variáveis que faltavam, gerei uma tabela dinâmica no looker studio e calculei o desvio padrão por ela, agora, estou gerando um histograma pois, devido os números encontrados pelos quartis nas variáveis de dias de atraso no pagamento, creio que o bloxpot não seja o ideal para visualizar, mas pelo histograma, consigo visualizar a ocorrência de empréstimos e atrasos por idade, creio que esteja certo, pois tenho as variáveis e a frequência que isso ocorre, a única métrica de tempo são as variáveis de atraso, infelizmente, mas ainda sim é possível visualizar a frequência que isso ocorre para cada idade, o que já é um ponto investigativo para definir quais clientes tem mais risco e quais tem menos.
    
    Agora, só preciso saber se a fora que fiz está correta, creio que sim, porém também creio que o ideal seja calcular separadamente cada atraso em um gráfico diferente para utilizar o histograma e somente na apresentação trazer um comparativo.
    
    Este foi o que fiz:
    
    (Importante ressaltar que também achei interessante agrupar idades para visualizar melhor).
    
    ![Captura de Tela (86).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/cfb915d5-4f8b-497b-aa5f-caa7ccfe11e1/5f7f51d7-ab96-4076-8e72-ae77c5e49b27.png)
    
    Já este é um exemplo de um conteúdo que busquei:
    
    ![Captura de Tela (84).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/bdd32ce1-f3dc-45fc-ada5-a94cff1d083a/eb3c5e5d-6df4-4a04-8c8d-aa611a7034ab.png)
    
    Um pouco do conteúdo apresentado:
    
    > **O que é histograma?**
    > 
    > 
    > Um histograma é 
    > uma espécie de gráfico de barras que demonstra uma distribuição de 
    > frequências. No histograma, a base de cada uma das barras representa uma
    >  classe e a altura representa a quantidade ou frequência absoluta com 
    > que o valor de cada classe ocorre. Ao mesmo tempo, ele pode ser 
    > utilizado como um indicador de dispersão de processos.
    > 
    > Quando você precisa apresentar ou tirar conclusões de um grande 
    > conjunto de dados e está trabalhando com conceitos envolvendo 
    > frequências, sejam absolutas ou relativas, o histograma é o melhor 
    > caminho a se tomar. Ele nos auxilia com a representação gráfica dos 
    > conjuntos de dados de forma mais amigável, tornando mais fácil a 
    > visualização de onde a maioria dos valores se concentram.
    > 
    > É útil construir um histograma quando você deseja:
    > 
    > - **Resumir grandes conjuntos de dados de forma visual:** Muitas vezes quando utilizamos tabelas não é tão fácil tirar
    > conclusões. Nós podemos facilitar nosso trabalho e ganhar muito mais
    > tempo e eficiência utilizando um histograma.
    > - **Comparar os resultados:** É possível, com o auxílio do histograma, rapidamente comparar os
    > resultados e, com o auxílio do eixo y, conhecer, se houver, quais
    > colunas ultrapassaram os limites que você precisava ou não.
    > - **Comunicar as informações graficamente:** Tanto as pessoas da sua equipe, quanto os clientes, podem ver
    > facilmente os valores que ocorrem com mais frequência. Quando você usa
    > um histograma para resumir grandes conjuntos de dados ou para comparar
    > resultados você está utilizando uma poderosa ferramenta de comunicação.
    
- TESTE (REMEMBER) QUARTIS
    
    
    ```
    SELECT
      APPROX_QUANTILES(last_month_salary_media_mod,4),
      APPROX_QUANTILES(last_month_salary_media_mod,3),
      APPROX_QUANTILES(last_month_salary_media_mod,2),
      APPROX_QUANTILES(last_month_salary_media_mod,1)
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Fiz um pequeno teste para recordar como essa fórmula funcionava; o número determina quantas divisões você quer no seu resultado, sendo o 4, número que te mostra todos os valores de quartis e mediana.
    
- CALCULO QUARTIS PARA CATEGORIZAÇAO
    
    
    ```
    SELECT
      APPROX_QUANTILES(last_month_salary_media_mod,4),
      APPROX_QUANTILES(Total_emprestimo,4),
      APPROX_QUANTILES(debt_ratio_media,4),
      APPROX_QUANTILES(number_times_delayed_payment_loan_30_59_days,4),
      APPROX_QUANTILES(more_90_days_overdue,4),
      APPROX_QUANTILES(using_lines_not_secured_personal_assets_media,4)
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    ![Captura de Tela (74).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/f666642d-a2b5-49f3-a016-64548b40f23b/4bfe4136-7ddd-483f-9438-80c65e3f4a34.png)
    
    ![Captura de Tela (75).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/c5968368-2d1e-4580-9713-f33dd1847ab5/aced27cb-ac71-42c3-80f2-65d89b5d5962.png)
    
    tabela temporaria:
    
    ```
    WITH data AS(
      SELECT
        last_month_salary_media_mod,
        Total_emprestimo,
        debt_ratio_media,
        number_times_delayed_payment_loan_30_59_days,
        more_90_days_overdue,
        using_lines_not_secured_personal_assets_media
      FROM `dataset_banco.Informacoes_Usuario`
    )
    SELECT
      APPROX_QUANTILES(last_month_salary_media_mod,4) AS lms_quartis,
      APPROX_QUANTILES(Total_emprestimo,4) AS te_quartis,
      APPROX_QUANTILES(debt_ratio_media,4) AS drm_quartis,
      APPROX_QUANTILES(number_times_delayed_payment_loan_30_59_days,4) AS ntdpl3059_quartis,
      APPROX_QUANTILES(more_90_days_overdue,4) AS m90do_quartis,
      APPROX_QUANTILES(using_lines_not_secured_personal_assets_media,4) AS ulnspam_qaurtis
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
- CORRELAÇÃO VARIAVEIS NUMERICAS
    
    ```
    SELECT
     CORR(age, number_dependents_mod) AS corr_10,
     CORR(age, last_month_salary_media_mod) AS corr_11,
     CORR(age, Total_emprestimo) AS corr_12,
     CORR(age, debt_ratio_media) AS corr_13,
     CORR(age, number_times_delayed_payment_loan_30_59_days) AS corr_14,
     CORR(age, more_90_days_overdue) AS corr_15,
     CORR(age, using_lines_not_secured_personal_assets_media) AS corr_16,
    
    CORR(Total_emprestimo, number_dependents_mod) AS corr_20,
    CORR(Total_emprestimo, debt_ratio_media) AS corr_21,
    CORR(Total_emprestimo, number_times_delayed_payment_loan_30_59_days) AS corr_22,
    CORR(Total_emprestimo, more_90_days_overdue) AS corr_23,
    CORR(Total_emprestimo, using_lines_not_secured_personal_assets_media) AS corr_24,
    CORR(Total_emprestimo, default_flag) AS corr_25,
    
    CORR(debt_ratio_media, number_times_delayed_payment_loan_30_59_days) AS corr_30,
    CORR(debt_ratio_media, more_90_days_overdue) AS corr_31,
    CORR(debt_ratio_media, using_lines_not_secured_personal_assets_media) AS corr_32,
    CORR(debt_ratio_media, default_flag) AS corr_33,
    
    CORR(number_times_delayed_payment_loan_30_59_days, more_90_days_overdue) AS corr_40,
    CORR(number_times_delayed_payment_loan_30_59_days, using_lines_not_secured_personal_assets_media) AS corr_41,
    CORR(number_times_delayed_payment_loan_30_59_days, default_flag) AS corr_42
    
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    ![Captura de Tela (82).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/327ad7fd-16d6-40b3-be47-12199ca5a5af/d56ff4c4-3f29-45df-ba14-890e8bd1cb6f.png)
    
    ![Captura de Tela (83).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/9b618d51-b3b1-4b66-8a72-3f4a7bcac595/bdd6c954-d00a-4da8-a229-3bce06da4ede.png)
    
    ![Captura de Tela (77).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/f35dca5e-43c6-4bff-90bf-2ee5b463270d/3b69b678-a9c4-4632-a083-e34b4b159dd1.png)
    
    ![Captura de Tela (78).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/506d19fa-bbd2-47e7-883e-64fe54d4b84e/81cedfe9-a3ff-4c86-a6b1-1909f76502fa.png)
    
    ![Captura de Tela (79).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/530258c5-3366-4f84-b828-ace79dc7c6d8/2b6de98d-f32f-4a70-ba8e-74308ed4698e.png)
    
    ![Captura de Tela (80).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/853524aa-5179-44fe-b04f-5d301012913c/7b73868d-8be9-4998-93bf-986cdad26825.png)
    
    ![Captura de Tela (81).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/f944ca3f-268c-411e-8168-147528ce22c9/80004e69-b03d-4ffc-bdc0-53dc7c6f63c0.png)
    

*Ainda não finalizei esse sprint, pretendo corrigir algumas coisas, apesar de ter realizado os sub tópicos, eles não foram realizados da maneira correta. Na verdade, é importante dar uma atenção para dois pontos nessa parte do projeto, que foram exatamente os pontos que não consegui compreender no projeto anterior:*

- *Gráficos de dispersão*
- *Histogramas*

*Felizmente, agora tenho tempo e a mente mais clara para compreender melhor o que estava fazendo e além de reproduzir esses gráficos, também conseguirei entende-los.*

---

## Aplicar Técnica de Análise

- 04/06
    
    Essa semana foi um pouco corrida, não consegui parar no domingo ou não segunda para estudar mas consegui estudar um pouco hoje sobre gráficos de dispersão e compreendi melhor como ler eles. Para isso assisti vídeos a respeito e compartilhei com minhas colegas.
    
- GRÁFICOS DE DISPERSÃO
    
    Gráficos de dispersão são uma visualização de como as variáveis se comportam quando correlacionadas, mas é importante ressaltar: correlação não necessariamente indica uma afirmação sobre causa e efeito de uma variável para outra, ela mostra apenas que há uma relação entre ambas.
    
    Da mesma maneira que a visualização da correlação no BigQuery funciona em tabela, nós conseguimos visualizar essa correlação através de um gráfico.
    
    É possível enxergar por exemplo quando a correlação é positiva, pois aí teremos uma crescente nos dois eixos, ou seja nas duas variáveis, apresentadas no eixo x e no eixo y, logo, se o eixo x crescendo eixo y tende a crescer também.
    
    Já numa correlação negativa, enquanto um eixo apresenta crescimento, o outro apresenta uma diminuição.
    
    Por fim, temos também uma apresentação de reta quase perfeita quando a correlação é chamada de positiva perfeita, isto é, há uma alta correlação entre as variáveis, implicando num aumento similar em ambas que forma uma reta no gráfico.
    
    Agora, caso aconteça a formação de uma outra figura que não uma reta ou crescente direcionada, então não temos uma correlação linear e sim uma de outro tipo.
    
- HISTOGRAMAS
    
    Apesar de histogramas serem feitos utilizando gráfico de barras, nem todo gráfico de barras pode ser considerado um histograma. Isso porque o histograma consiste em mostrar os números e frequências num intervalo de tempo, logo, não há espaçamento dentre as barras e os intervalo vem de uma variável numérica continua, como idade, por exemplo: 
    
    21|—| 24|—| 27… e assim por diante.
    
    Logo, apesar do gráfico que usei mostrar a frequência em que aquele grupo de idade ocorre, ele não mostra intervalos da maneira correta e sim uma contagem de vezes que pessoas disseram ter 24 anos, por exemplo, o que apesar de ser parecido, não é a mesma coisa.
    
    Bem, percebi que o que falta para ter um histograma é o intervalo de cada caso, por isso vou separar os intervalos para assim criar um histograma corretamente.
    
    - Coletar dados
    - Ordenalos
    - Criar intervalos
- INTERVALO PARA HISTOGRAMA
    
    ![Captura de Tela (87).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/8f3a38f2-2240-444a-a7a6-01eb3de48a46/a45be5cb-a7c6-43c4-a8c3-07249b462f3d.png)
    
    ![Captura de Tela (88).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/786619ec-7ca5-4fa2-aed3-3088a04dba8c/70efa1c2-5df3-42c2-861f-61d1bca2af39.png)
    
    ```
    CREATE OR REPLACE TABLE `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    AS
    SELECT
      *,
      CASE
        WHEN age <=21 THEN "18 A 21 ANOS"
        WHEN age <=44 THEN "21 A 44 ANOS"
        WHEN age <=53 THEN "44 A 53 ANOS"
        WHEN age <=63 THEN "53 A 63 ANOS"
        WHEN age <=109 THEN "63 A 109 ANOS"
        ELSE "NULO"
      END AS Intervalos_hist
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    Tenho os dados coletados, a organização destes e os intervalos determinados. Se olhar para a lateral (eixo y) podemos visualizar a frequência em que ocorre a realização de empréstimos; agora sim, creio que construi um histograma.
    
- RISCO RELATIVO
    
    Antes de mais nada é importante saber o total de valores para cada intervalo de idade na coluna.
    
    ```
    SELECT
      COUNT(*) AS Total_por_idade,
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    WHERE Intervalos_hist = "21 A 44 ANOS"
    
    ```
    
    <aside>
    🛠 A lógica dessa fórmula é: selecionar todos os valores da tabela (também pode ser utilizado o nome da coluna especifica dentro do parênteses) onde, na coluna “Intervalos_hist”, está representado como a condição sugere. 
    Ou seja, sem precisar separar esta variável em outras colunas eu posso encontrar quantos clientes existem ali para cada intervalo, por exemplo: tenho 43 clientes que possuem entre 18 e 21 anos; o próximo passo é descobrir quantos, desses 43 clientes, são inadimplentes e assim calcular para cada grupo.
    
    </aside>
    
    RESULTADOS:
    
     (default_flag) 18 - 21: 43
    
     (default_flag) 21 - 44: 79412
    
    (default_flag) 44 - 53: 73212
    
    (default_flag) 53 - 63: 81226
    
     (default_flag) 63 - 109: 71442
    
    ```
    SELECT
      COUNT(default_flag) AS Total_inadimplentes,
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    WHERE Intervalos_hist = "18 A 21 ANOS" AND default_flag = 1
    
    ```
    
    <aside>
    🛠 Aqui, eu possuo duas condições, basicamente: “quantas pessoas nesta faixa etária apresentam risco de inadimplência?”
    
    </aside>
    
    RESULTADOS:
    
    Inadimplentes (default_flag) 18 - 21: 0
    
    Inadimplentes (default_flag) 21 - 44: 1988
    
    Inadimplentes (default_flag) 44 - 53: 1272
    
    Inadimplentes (default_flag) 53 - 63: 727
    
    Inadimplentes (default_flag) 63 - 109: 326
    
    Agora realizamos o calculo:
    
    [Taxa de incidência do grupo exposto/ Total do grupo exposto]
    
    | idades | total por idade | total inadimplentes | total sem risco |
    | --- | --- | --- | --- |
    | 18 - 21 | 43 | 0 | 43 |
    | 21 - 44 | 79412 | 1988 | 74424 |
    | 44 - 53 | 73212 | 1272 | 71940 |
    | 53 - 63 | 81226 | 727 | 80499 |
    | 63 - 109 | 71442 | 326 | 71116 |
    
    0/43 = 0
    
    1988/79412 = 0,025033
    
    1272/73212 = 0,017374
    
    727/81226 = 0,008950
    
    326/71442 = 0,0045
    
    Em sequencia, fazemos o mesmo para o grupo não exposto que é determinado por quartil, por exemplo:
    
    grupo exposto: quartil 1 (18 - 21): 0
    
    grupo não exposto: q2 + q3 + q4 (21 - 109): 4313
    
    pegamos o valor da segunda linha e dividimos pelo total de pessoas que correspondem a essas idades: 
    
    (inadimplentes q2 + q3 + q4) / (total q2+ q3 +  q4)
    
    | grupo exposto | gp não exposto | - | grupo exposto | gp não exposto | total gp n exposto |
    | --- | --- | --- | --- | --- | --- |
    | q0 | q1 q2 q3 q4 | - | 0 | 4313 | 4313 |
    | q1 | q0 q2 q3 q4 | - | 1988 | 2325 | 4313 |
    | q2 | q0 q1 q3 q4 | - | 1272 | 3041 | 4313 |
    | q3 | q0 q1 q2 q4 | - | 727 | 3586 | 4313 |
    | q4 | q0 q1 q2 q3 | - | 326 | 3987 | 4313 |
    
    Temos os valores dos grupos não expostos para cada quartil, agora podemos pegar os valores não expostos e dividir pelo total:
    
    -q0: 1
    
    -q1: 0,53
    
    -q2: 0,70
    
    -q3: 0,83
    
    -q4: 0,92
    
    agora que temos a diferença entre os grupos expostos e não expostos, realizamos o calculo:
    
    [incidência do grupo exposto] / [incidência no grupo não exposto]
    
    q0: 0/1 = 0
    
    q1:  0,025033/0,53 = 0,47232
    
    q2: 0,017374/0,70 = 0,02482
    
    q3: 0,008950/0,83 = 0,01078
    
    q4: 0,0045/0,92 = 0,004891
    
    A intenção desse calculo é comparar os valores de incidência do grupo exposto co o grupo não exposto.
    
    Agora, com esses comparativos, temos uma melhor visualização de  qual grupo tem maior incidência de ‘maus pagadores”, que seria o q1 a.k.a. pessoas dentre 21 e 44 anos, essas pessoas tem uma incidência maior de devedores/maus pagadores.
    
    Fun fact: além de serem classificados com esse alerta, as pessoas entre 21 e 44 anos também são as com maior índice de empréstimos feitos, tendo uma frequência de 57 a cada 60 pessoas.
    
    ![Captura de Tela (89).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7bb4ff67-878c-4a87-9c1c-f64dc250cae1/caa7fe2d-8757-4fe0-be0b-8c233df78597/19513c0b-ed82-41de-a082-e394eb8d661e.png)
    
    Agora, preciso seguir com essa categorização para o ultimo salário também:
    
    | quartil | salario | total por quartil | inadimplentes dessa classe | total sem risco |
    | --- | --- | --- | --- | --- |
    | q0 | 0 - 1000 | 525 | 10 | 515 |
    | q1 | 1000 - 4500 | 75068 | 1743 | 73325 |
    | q2 | 4500 - 6809 | 128754 | 1709 | 127045 |
    | q3 | 6809 - 8000 | 26103 | 340 | 25763 |
    | q4 | 8000 - 20000 | 74885 | 511 | 74374 |
    
    Q0 = 0,019047
    
    Q1 = 0,023218
    
    Q2 = 0,013273
    
    Q3 = 0,013025
    
    Q4 = 0,006823
    
    | GRUPO EXPOSTO | NÃO EXPOSTO | TOTAL DE GRUPO NÃO EXPOSTO |
    | --- | --- | --- |
    | 10 | 4303 | 4313 |
    | 1743 | 2570 | 4313 |
    | 1709 | 2604 | 4313 |
    | 340 | 3973 | 4313 |
    | 511 | 3802 | 4313 |
    
    NÃO EXPOSTO:
    
    Q0 = 0,99768
    
    Q1 = 0,59587
    
    Q2 = 0,60375
    
    Q3 = 0,92116
    
    Q4 = 0,88152
    
    DIFERENÇA ENTRE ELES:
    
    Q0 = 0,0190
    
    Q1 = 0,0389 ← A INCIDÊNCIA É MAIOR AQUI
    
    Q2 = 0,0219
    
    Q3 = 0,01112
    
    Q4 = 0,0077
    
    QUANTIDADE DE EMPRÉSTIMOS:
    
    | QUARTIS | QNTD EMPRESTIMO | TOTAL POR QUARTIL | TOTAL INADIMPLENTES | SEM RISCO |
    | --- | --- | --- | --- | --- |
    | Q0 | 0 - 1 | 1065 | 30 | 1035 |
    | Q1 | 1 - 7 | 78301 | 1659 | 76642 |
    | Q2 | 7 - 10 | 72157 | 853 | 71304 |
    | Q3 | 10 - 15 | 88143 | 1135 | 87008 |
    | Q4 | 15 - 57 | 65669 | 636 | 65033 |
    
    Q0 = 0,028
    
    Q1 = 0,021
    
    Q2 = 0,011
    
    Q3 = 0,012
    
    Q4 = 0,009
    
    | GRUPO EXPOSTO | NÃO EXPOSTO | TOTAL DE GRUPO NÃO EXPOSTO |
    | --- | --- | --- |
    | 30 | 4283 | 4313 |
    | 1659 | 2654 | 4313 |
    | 853 | 3460 | 4313 |
    | 1135 | 3178 | 4313 |
    | 636 | 3677 | 4313 |
    
    NÃO EXPOSTO:
    
    Q0 = 0,993
    
    Q1 = 0,615
    
    Q2 = 0,802
    
    Q3 = 0,736
    
    Q4 = 0,852
    
    DIFERENÇA ENTRE ELES:
    
    Q0 = 0,0281
    
    Q1 = 0,0341 ← MAIOR INCIDÊNCIA
    
    Q2 = 0,0137
    
    Q3 = 0,0163
    
    Q4 = 0,0105
    
- CATEGORIZAÇÃO
    
    Vou categorizar por números assim já tenho um score para cada cliente.
    
    | quartil | idade | ultimo salario | total de emprestimos | media (debt_ratio) | numero de atraso (30-59) dias | mais de 90 dias de atraso | (ulnsamedia) |
    | --- | --- | --- | --- | --- | --- | --- | --- |
    | q0 | 18 - 21 , 0 | 0 - 1000 , 0 | 0 - 1 , 1(risco) | 10 | 0 | 0 | 1 |
    | q1 | 21 - 44 , 2 (m.p) | 1000 - 4500 , 2 (m.p) | 1 - 7 , 2(m.p) | 352 | 0 | 0 | 6 |
    | q2 | 44 - 53 , 1(risco) | 4500 - 6809 , 1(risco) | 7 - 10 , 0 | 352 | 0 | 0 | 6 |
    | q3 | 53 - 63 , 0 | 6809 - 8000 , 0 | 10 - 15 , 0 | 352 | 0 | 0 | 6 |
    | q4 | 63 - 109 , 0 | 8000 - 20000 , 0 | 15 - 57 , 0 | 2000 | 98 | 98 | 6 |
    
    0 =  bom pagador
    
    2 = mau pagador
    
    1 = RISCO m.p.
    
    SOMA: 
    
    4 a 6 pontos =  categoria de risco, a pessoa se encontra em pelo menos 1 classificação como de mau pagador e 1 de risco. (RED)
    
    2 a 3 pontos = a pessoa está na margem de risco, é importante ficar atento (YELLOW) 
    
    0 a 1 ponto =  a pessoa não apresenta risco para se tornar mau pagador. (GREEN)
    
    SOMA SCORE:
    
    ```
    CREATE OR REPLACE TABLE `dataset_banco.Informacoes_Usuario`
    AS
    SELECT
     *,
     (classificacao_rr_age+classificacao_rr_salary+classificacao_rr_emprestimos) AS SCORE
    FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    ```
    
    CATEGORIZAÇÃO FLAG:
    
    ```
    CREATE OR REPLACE TABLE `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    AS
    SELECT
      *,
      CASE
        WHEN SCORE BETWEEN 4 AND 6 THEN "RED"
        WHEN SCORE BETWEEN 2 AND 3 THEN "YELLOW"
        WHEN SCORE <=1 THEN "GREEN" 
        ELSE "NULO"
        END AS score_flags
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
    
    ```
    
- VALIDAÇÃO DE HIPÓTESES
    - Hipótese:
    - Os mais jovens correm um risco maior de não pagamento.
    
    R: Positiva fraca, tendo em vista que a maior ocorrência se encontra na faixa de 21-44, mas antes dessa faixa, temos clientes mais novos que não possuem ocorrência de inadimplência.
    
    - Pessoas com mais empréstimos ativos correm maior risco de serem maus pagadores.
    
    R: Negativa forte, maior ocorrência de maus pagadores se encontra entre 1 a 7 empréstimos.
    
    - Pessoas que atrasaram seus pagamentos por mais de 90 dias correm maior risco de serem maus pagadores.
    
    R: Não criei uma categorização para os dias de atraso (acho melhor fazer em breve, creio que possa ser necessária para visualizar melhor) mas dos clientes que apresentam a RED flag, quase nenhum ou nenhum apresenta um atraso nos dias de pagamento…**** correção: através dos gráficos do dashboard pude confirmar essa hipotese, tendo em mente que, de 1.142 pessoas que atrasaram pelo menos uma vez seus pagamentos (por exemplo), 606 delas estão classificadas como RED flags de acordo com o meu score.
    

*Para a minha surpresa, finalizo aqui o marco 1 e como ficaram algumas pontas soltas nessa segmentação, pretendo explora-las mais para ter uma visão mais assertiva dos dados apresentados e trazer também uma apresentação mais clara.*

---

# MARCO 2

*Finalmente cheguei ao marco 2!*

!https://media0.giphy.com/media/o75ajIFH0QnQC3nCeD/giphy.gif?cid=7941fdc61q1epdnujzzjbw30hp3l0c98hlbq7kgl4x54xjuw&ep=v1_gifs_search&rid=giphy.gif&ct=g

*Esperei isso durante a minha vida toda :’) (desde Março/24) e finalmente, consegui alcançar! Um minuto de silêncio para apreciar esse momento incrível graças a organização bem aplicada que tive gosto em aderir! (Parabéns Brendinha!) Agora podemos prosseguir para o tão aguardado Marco 2.*

- 10/06
    
    Essa semana que passou foi bem corrida e cheia de coisas a fazer, mas hoje, retorno para o projeto (01:19 a.m.) e minha meta hoje é compreender o conceito e aplicar a segmentação. 
    

- 12/06
    
    Neste dia maravilhoso… vou corrigir algumas coisas da  minha tabela.
    
    Ontem tomei uma decisão importante sobre o projeto: não vou entregar o marco 2, vou tomar a mesma rota que tomei nos anteriores pois estamos no último mês e eu gostaria muito de dar uma atenção maior ao job preparation e focar no último projeto que será em dupla. Mas só começarei o próximo projeto quando fizer o upgrade na máquina, isto é: acrescentar os slots de memória e ssd.
    
    Enquanto isso posso ir estudando a matriz de confusão, tenho tempo e isso me deixa contente :)  
    
    Hoje, preciso remover a coluna “genero” e a coluna “loan_type” pra ter os dados mais organizados.
    

---

- 23/06
    
    Eu fiquei quase duas semanas paradas, uma para manutenção do pc que de primeira não havia dado totalmente certo e depois consegui a peça certa, agora eles está rapido e funcional; a segunda semana eu estava com dengue… bom, ainda estou me recuperando, então vou aproveitar hoje (domingo) para corrigir essas pontas soltas do projeto e ai montar minha apresentação.
    
    - FORMULA AGRUPAR INFORMAÇÕES POR USUARIO
        
        ```
        CREATE OR REPLACE TABLE `dataset_banco.Informacoes_Usuario`AS
        SELECT
        user_id,
        MAX(age) AS age,
        MAX(number_dependents_mod) AS number_dependents_mod,
        MAX (last_month_salary_media_mod) AS last_month_salary_media_mod,
        MAX (Total_emprestimo) AS Total_emprestimo,
        MAX (debt_ratio_media) AS debt_ratio_media,
        MAX (number_times_delayed_payment_loan_30_59_days) AS number_times_delayed_payment_loan_30_59_days,
        MAX (more_90_days_overdue) AS more_90_days_overdue,
        MAX (using_lines_not_secured_personal_assets_media) AS using_lines_not_secured_personal_assets_media,
        MAX (default_flag) AS default_flag,
        MAX (default_flag_name) AS default_flag_name,
        MAX (Intervalos_hist) AS Intervalos_hist,
        MAX (Intervalos_salary) AS Intervalos_salary,
        MAX (Intervalos_emprestimos) AS Intervalos_emprestimos,
        MAX (classificacao_rr_age) AS classificacao_rr_age,
        MAX (classificacao_rr_salary) AS classificacao_rr_salary,
        MAX (classificacao_rr_emprestimos) AS classificacao_rr_emprestimos,
        MAX (SCORE) AS SCORE,
        MAX (score_flags) AS score_flags
        FROM `local-parsec-424021-r9.dataset_banco.Informacoes_Usuario`
        
        GROUP BY user_id
        ```
        
    
    Dashboard pronto (02:20 am) amanhã (mais tarde) faço a apresentação.
    
- 24/06
    
    Hoje finalizei a apresentação! link do video:
    

https://www.loom.com/share/7dc6c3b4a02d41619393132e9ec2d8a9?sid=95dfee93-a45b-4304-aa63-e13c18e1b984

O dashboard: https://lookerstudio.google.com/reporting/241d4a0c-9edd-4802-bc9b-665e08402741
