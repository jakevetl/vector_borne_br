
# Análise de dados climáticos e correlações com casos de arboviroses

Será que com os dados obtidos do seguinte [database](https://www.kaggle.com/datasets/joaopedromedeiros/climatechikungunya-zika-and-dengue?select=all_arb_cid.csv) é possível prevermos quando é esperado um aumento no caso de arboviroses na microregião da Zona da Mata/MG?

DICIONÁRIO - SINAM

1. **Unnamed: 0**: Índice da linha no DataFrame (pode ser descartado se não for necessário).

2. **CLASSI_FIN**: Classificação final do caso. No dicionário que encontrei do SINAM, há apenas esclarecimento sobre o que significa as pontuações de classificação final em DENGUE, não fala sobre as outras duas, limitando a utilização do dado.

Seria algo como:

DENGUE
5.descartado
10.Dengue
11.Dengue com sinais de alarme
12.Dengue grave
13.Chikungunya

3. **codigo_municipio_completo**: Código completo do município. No exemplo, 3139409.

4. **COMUNINF**: Código da comunidade indígena (se aplicável). No exemplo, NaN (não se aplica).

5. **COPAISINF**: Código do país de infecção (se diferente do Brasil). No exemplo, NaN (não se aplica).

6. **COUFINF**: Código da unidade federativa de infecção. No exemplo, NaN (não se aplica).

7. **CRITERIO**: Critério de confirmação do caso. No dicionário que encontrei do SINAM, há apenas esclarecimento sobre o que significa as pontuações de critério em DENGUE, não fala sobre as outras duas, limitando a utilização do dado.

Seria algo como:
DENGUE
5. Descartado
10. Dengue
11. Dengue com sinais de alarme
12. Dengue grave
13. Chikungunya

8. **CS_ESCOL_N**: Escolaridade do paciente. No exemplo, 9.0 (pode representar um nível de escolaridade específico).

43.Analfabeto  
1. 1ª a 4ª série incompleta do EF 
2. 4ª série completa do EF ( antigo 1° grau) 
3. 5ª à 8ª série incompleta do 
EF (antigo ginásio ou 1° grau) 
4. Ensino fundamental completo (antigo ginásio ou 1° grau) 
5. Ensino médio incompleto (antigo colegial ou 2° grau) 
6. Ensino médio completo (antigo colegial ou 2° grau) 
7. Educação superior incompleta  
8. Educação superior completa  
9. Ignorado 
10. Não se aplica 

9. **CS_FLXRET**: Fluxo de retorno, identifica se o registro está habilitado ou foi enviado pelo fluxo de retorno para o municipio de residência.

0.Não
1.Habilitado para envio
2.enviado

10. **CS_GESTANT**: Estado de gestação (se a paciente está grávida). No exemplo, 0.0 (não está grávida).

1.1o trimestre
2.2o trimestre
3.3o trimestre
4.Idade gestacional ignorada
5.Não
6.Não se aplica
9.Ignorado


Campo Obrigatório se sexo = F 
 
Se sexo= Feminino e idade 
menor ou igual a 10 anos, o 
campo é preenchido 
automaticamente com a 
categoria 6 = Não se aplica 
 
Se Sexo=Masculino o campo é
preenchido automaticamente
com 6 Não se Aplica;

11. **CS_RACA**: Raça/cor do paciente. No exemplo, 5.0 (pode representar uma categoria específica de raça/cor).

1.Branca
2.Preta
3.Amarela
4.Parda
5.Indigena
9.Ignorado

12. **CS_SEXO**: Sexo do paciente. No exemplo, 3.0 (provavelmente 'F' para feminino).

M- Masculino 
F- Feminino 
I- Ignorado 

13. **DOENCA_TRA**: Doença tratada. No exemplo, 2.0 (pode representar um código de doença específica).

1.Sim
2.Não
9.Ignorado

Campo habilitado se 
Classificação final=1, 2 ou null. 
 
Não permite a opção óbito pelo 
agravo notificado se 
classificação final= 2 ou null. 

14. **DT_ENCERRA**: Data de encerramento do caso. No exemplo, 2013-01-25.

15. **DT_INVEST**: Data de início da investigação. No exemplo, 2013-01-03.

16. **DT_NOTIFIC**: Data de notificação do caso. No exemplo, 2013-01-03.

17. **DT_OBITO**: Data de óbito (se aplicável). No exemplo, NaN (não se aplica).

18. **DT_SIN_PRI**: Data de início dos sintomas. No exemplo, 2012-12-30.

19. **EVOLUCAO**: Evolução do caso (cura, óbito, etc.). No exemplo, 1.0 (provavelmente 'cura').
1.Cura
2.Óbito por (doença)
3.Óbito por outras causas
9.Ignorado

20. **FLXRECEBI**: Recebimento do fluxo de dados. No exemplo, identifica se o registro foi recebido pelo fluxo de retorno. Coloca a estrutura do no atribuido pelo sistema

21. **ID_AGRAVO**: Identificação do agravo (doença). No exemplo, A90 (Código CID-10 para dengue).

22. **ID_MN_RESI**: Identificação do município de residência. No exemplo, 313940.

23. **ID_MUNICIP**: Identificação do município do caso. No exemplo, 313940.

24. **ID_PAIS**: Identificação do país. No exemplo, 1 (provavelmente Brasil).

25. **ID_REGIONA**: Identificação da região. No exemplo, 1454.

26. **ID_RG_RESI**: Identificação da região de residência. No exemplo, 1454.

27. **mesorregiao_geografica**: Mesorregião geográfica do município. No exemplo, 12 (provavelmente um código para Zona da Mata).

28. **microrregiao_geografica**: Microrregião geográfica do município. No exemplo, 61 (provavelmente um código para Manhuaçu).

29. **municipio**: Código do município. No exemplo, 39409.

30. **NDUPLIC_N**: Indicador de duplicidade (provavelmente se o caso é duplicado). No exemplo, NaN (não duplicado).
0. ou null - não identificado
1.Não é duplicidade (não listar)
2.Duplicidade(não contar)

31. **nome_mesorregiao**: Nome da mesorregião. No exemplo, Zona da Mata.

32. **nome_microrregiao**: Nome da microrregião. No exemplo, Manhuaçu.

33. **nome_municipio**: Nome do município. No exemplo, Manhuaçu.

34. **nome_uf**: Nome da unidade federativa (estado). No exemplo, Minas Gerais.

35. **NU_ANO**: Ano de notificação. No exemplo, 2013.

36. **NU_IDADE_N**: Idade do paciente. No exemplo, 4016 (provavelmente em meses ou dias).
A composição da variável 
obedece o seguinte critério: 1o dígito: 
1. Hora 
2. Dia 
3. Mês 
4. Ano 
 
Ex: 
3009 – nove meses, 
4018 – dezoito anos, 
2072 - setenta e dois dias, 
1010 - dez horas

37. **SEM_NOT**: Semana epidemiológica de notificação. No exemplo, 201301 (semana 1 de 2013).

38. **SEM_PRI**: Semana epidemiológica de início dos sintomas. No exemplo, 201301 (semana 1 de 2013).

39. **SG_UF**: Sigla da unidade federativa (estado) de residência. No exemplo, 31 (provavelmente Minas Gerais).

40. **SG_UF_NOT**: Sigla da unidade federativa (estado) de notificação. No exemplo, 31 (provavelmente Minas Gerais).

41. **TP_NOT**: Tipo de notificação. No exemplo, 2 (provavelmente um código específico).
1.Negativa
2.Individual
3.Surto
4.Agregado

42. **TPAUTOCTO**: Tipo de autoctonia (se a infecção foi adquirida no município de residência). 
1.Sim
2.Não
3.Indeterminado
classificação final=1(confirmado) 
 
Se o campo for preenchido com 
1 (sim), o sistema preenche 
automaticamente os campos de 
autoctonia (UF, País e Município 
provável da fonte de infecção) 
com os valores registrados nos 
campos da notificação e habilita 
para o usuário preencher os 
campos distrito e bairro (se país 
de residência não for Brasil, a 
UF e município de infecção 
podem ficar em branco). 
 
Se o campo for preenchido com 
2 (Não), o sistema  habilita para 
o usuário preencher todos os 
campos de autoctonia (UF, País 
e Município, distrito e bairro 
provável da fonte de infecção). 
 
Se o campo for preenchido com 
3 (Indeterminado), pular os 
campos de autoctonia (UF, País, 
 Município, Distrito e Bairro 
provável da fonte de infecção). 
 
Campo habilitado se 
classificação final= 1 ou null. 
 
Quando a classificação final for 
preenchida com 2(descartado) 
os dados desse campo são 
automaticamente apagados 
 
Retirada observação. 


43. **uf**: Unidade federativa (estado). No exemplo, 31 (provavelmente Minas Gerais).

44. **X**: Coluna possivelmente reservada para uso futuro ou erro. No exemplo, 2967.

45. **X.1**: Coluna possivelmente reservada para uso futuro ou erro. No exemplo, 2967.

46. **tipo**: Tipo de dado (pode se referir ao tipo de registro ou agravo). No exemplo, dengue.

