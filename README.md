

# Trabalho de banco de dados baseado no Campeonato Mundial de Valorant VCT Lock'In São Paulo.

## As querys utilizadas no dashboard foram: [Dashborad](https://lookerstudio.google.com/reporting/3ce747b2-da56-457a-b245-594d45b5c859)
### os Dados do banco de dados: [Excel](https://docs.google.com/spreadsheets/d/1aJnXW9uWCcSHVW78dwRLXT-COAffwYq4_OcXyhuVoAo/edit?usp=sharing)

![image](https://raw.githubusercontent.com/Senac-Squad/Dashboard_Banco-de-Dados/main/dashboard.png)


### Quais as armas mais usadas?
```select WeapNome, WeapUsage from armas order by WeapUsage desc;```


### Quais os mapas mais usados no campeonato?
```select MapNome, MapPick from mapa order by MapPick desc;```


### Quais os players que mais abateram no campeonato?
```select Nome, K from jogadores order by K desc;```


### Quais os players que mais receberam melhor da partida?
```select j.Nome, count(p.MVP) from jogos p inner join jogadores j on j.JogadorId = p.MVP group by j.Nome order by count(p.MVP) desc;```


### Qual a quantidade de players de cada país?
```select Pais, count(Pais) from jogadores group by Pais order by count(Pais) desc;```


### Qual o placar da final?
```select j.PlacarTime1, j.PlacarTime2  from jogos j left join equipes e on j.Time1 =  e.EquipeId where j.JogoId > 73 order by j.JogoId;```
