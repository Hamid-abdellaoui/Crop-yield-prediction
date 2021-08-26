# crop-yield-predection
## Contenue du nootebook :
  > * #### 1. Data preparation & exploration <space><space>
  > * #### 2. Prediction des Temperatures  <space><space>
   >>> * SARIMA <space><space><space><space>
  > * #### 3. Prediction des précipétations <space><space>
   >>>  * ARIMA <space><space><space><space>
   >>>  * LSTM <space><space><space><space>
  > * #### 4. prédiction du rendement agricole <space><space>
   >>> * Vector auto-regressive model - VAR <space><space><space><space>
   >>> * Multiple linear regression <space><space><space><space>
  




## Théories derière les modèles et les techniques utilisés
### <font color='#03d7fc' size=5>▶ Modèle Auto-Régressif (AR)</font>
Les modèles auto-régressifs fonctionnent en partant du principe que les valeurs passées ont un effet sur les valeurs actuelles. Les modèles AR sont couramment utilisés pour analyser la nature, l’économie et d’autres processus variables dans le temps. Tant que l’hypothèse tient, nous pouvons construire un modèle de régression linéaire qui tente de prédire aujourd’hui la valeur d’une variable dépendante, compte tenu des valeurs qu’elle avait les jours précédents. <br>
<img src='https://assets.moncoachdata.com/v7/moncoachdata.com/wp-content/uploads/2020/01/modele-ar.png?w=600'/> <br>

### <font color='#03d7fc' size=5>▶ Modèle de la Moyenne Mobile (MA)</font>
Supposez que la valeur de la variable dépendante du jour en cours dépend des termes d’erreur des jours précédents. La formule peut être exprimée sous cette forme :<br>
<img src='https://assets.moncoachdata.com/v7/moncoachdata.com/wp-content/uploads/2020/01/modele-moyenne-mobile-formule1.png?w=600'/> <br>
où μ est la moyenne de la série, les θ1, …, θq sont les paramètres du modèle et les εt, εt-1,…, εt-q sont les termes d’erreur de bruit. La valeur de q est appelée l’ordre du modèle MA. <br>
### <font color='#03d7fc' size=5>▶ Modèle de la Moyenne Mobile Auto-Régressive (ARMA)</font>
Le modèle ARMA est simplement la combinaison des 2 précédents modèles AR et MA : <br>
<img src='https://assets.moncoachdata.com/v7/moncoachdata.com/wp-content/uploads/2020/01/formule-modele-arma.png?w=600'/> <br>
### <font color='#03d7fc' size=5>▶ Modèle de la Moyenne Mobile Auto-Régressive Intégrée (ARIMA) </font>
Le modèle ARIMA ajoute une différence à un modèle ARMA. La différenciation soustrait la valeur actuelle de la précédente et peut être utilisée pour transformer une série temporelle en une série stationnaire. Par exemple, la différenciation du premier ordre traite des tendances linéaires et utilise la transformation zi = yi – yi-1. <br>
La différenciation du second ordre traite des tendances quadratiques et utilise une différence du premier ordre sur une différence du premier ordre, à savoir zi = (yi – yi-1) – (yi-1 – yi-2), et ainsi de suite. <br>

Trois entiers (p, d, q) sont généralement utilisés pour paramétrer les modèles ARIMA : <br>
<b>
* p : nombre de termes autorégressifs (ordre AR) 
* d : nombre de différences non saisonnières (ordre de différenciation)
* q : nombre de termes moyens mobiles (ordre MA)</b>
 <br>

### <font color='#03d7fc' size=5> ▶ Modèle SARIMA: Seasonal ARIMA </font><br>
SARIMA: Seasonal ARIMA ou ARIMA saisonnier est une extension du modèle ARIMA.
<img src='https://miro.medium.com/max/1400/0*hTDJbnnbhS3SDJvc.png' width=600/> <br>
Il permet de modéliser les séries temporelles comportant une composante saisonnière et désigné par 7 paramètres : <br>
<b>
* p, d, q : les même que ceux de ARIMA.
* P : ordre de la partie autorégressive saisonnière.
* D : ordre de la différence saisonnière.
* Q : ordre de la moyenne mobile saisonnière.
* m : la période de la composante saisonnière. <b> <br>


<img src='https://i.stack.imgur.com/NUA6V.png'  width=600/>
