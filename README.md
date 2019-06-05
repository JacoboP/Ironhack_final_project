# Ironhack_final_project
Academic project to value NBA draft class '19 in order to their performance in college

## Objetivos del proyecto

El objetivo del proyecto es determinar a partir de las estadísticas de los jugadores universitarios candidatos al draft de 2019 cuales de estos jugadores acabarán siendo elegidos entre los 5 primeros del draft y cuales acabarán jugando en algún momento de su carrera el partido de las estrellas.

## Preparación del proyecto

### Obtención de la información

Para la realización de este proyecto se ha conseguido la siguiente información.

    - Lista de jugadores universitarios que han confirmado que acudirán al draft de 2019. 
        - Este paso se ha realizado mediante scraping de la web de noticias: https://collegebasketball.nbcsports.com
        
    - Estadísticas de cada jugador que acudirá al draft 2019.
        - Por medio de scraping a la web: https://www.sports-reference.com/cbb
    
    - Lista de todos los jugadores que estuvieron en la NBA desde el año 2000.
        - Por medio de scraping a la web: https://www.sports-reference.com
        
    - Estadísticas de estos jugadores en época universitaria.
        - Por medio de scraping a la web: https://www.sports-reference.com/cbb
        
    - Información y estadísticas de los jugadores que han participado en el All Star.
        - Archivo .txt descargado de: https://www.basketball-reference.com/allstar
        
    - Información y jugadores del Draft de la NBA desde el año 2000.
        - Archivo .txt descargado de: https://www.basketball-reference.com/draft
        
Tras estos pasos guardamos dos DataFrame:

    - draft19_class.csv: Guarda todas las estadísticas de jugadores que serán seleccionables en el próximo draft
    
    - college_nba.csv: Guarda todas las estadísticas de epoca universitaría de jugadores que han juegan o han jugado en la NBA. Además guarda su 'pick' en su correspondiente draft y si ha sido All Star
        
### Limpieza de datos

Una vez obtenidos los DataFrame en los pasos anteriores procedemos a limpiar estos datos y a eliminar correlaciones entre columnas. Tras esto eliminamos columnas que no nos harán falta para el modelo y creamos dummies en los valores no numericos.
        
### Elección de modelo y entrenamiento
 
Con los DataFrame obtenidos aplicamos diferentes modelos a los datos para determinar cual es el que tiene mayor precisión. Los modelos utilizados han sido:

    1. Linear regresion 
    2. Logistic regresion 
    3. k-Neighbours k=3 
    4. k-Neighbours k=5 
    5. RandomForest 
    6. Gaussian Method
    7. SVC
    8. GradientBoostingClassifier
 
Tras esto al determinar que hay descompensación en los datos creamos valores sinteticos para poder entrenar el modelo con RandomForest tras hacer gridsearch.

### Aplicación del modelo a los datos

Tras obtener el mejor modelo posible aplicamos este al DataFrame con los jugadores seleccionables para el draft de 2019 obteniendo los siguientes resultados.
 


Código de referencia de siglas para las tablas.
       
    Name: Nombre del jugador
    G: Partidos jugados
    GS: Partidos jugados como titular
    MP: Minutos jugados
    FG: Tiros ejecutados por partido
    FGA: Tiros intentados por partido
    FG%: Porcentaje de acierto total de tiro
    2P: Tiros encestados de 2 puntos
    2PA: Tiros intentados de 2 puntos
    2P%: Porcentaje de acierto en tiros de 2
    3P: Tiros encestados de 3 puntos
    3PA: Tiros intentados de 3 puntos
    3P%: Porcentaje de acierto en tiros de 3
    FT: Tiros libres encestados
    FTA: Tiros libres intentados
    FT%: Porcentaje de acierto en tiros libres
    ORB: Rebotes ofensivos
    DRB: Rebotes defensivos
    TRB: Total de rebotes
    AST: Asistencias
    STL: Robos de balón
    BLK: Tapones
    TOV: Perdidas
    PF: Faltas personales
    PTS: Total de puntos
    SOS: Dificultad de calendario. Esta medida pondera la dificultad de los rivales en los partidos jugados
    POS: Posición en el campo

