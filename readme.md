#Css grid framework

Genera una o più griglie, con caratteristiche diverse per numero di colonne e spaziatura, 
ogni griglia è contraddistinta da una classe che funge da namespace.
Utilizzo:

    .make-grid( class{string}, colonne{int}, margin{%}, padding{% | px} );

Parametri:

- class: stringa che identifica la classe della riga
- colonne: intero, è il numero di colonne per la riga con classe .row.@class
- margin: se vuoi che le colonne abbiano un margin, impostalo qui (in percentuale!!). Default 0
- padding: se vuoi che le colonne abbiano un padding, impostalo qui. Default 0


Genera le seguenti classi:

**.row**: definisce una riga  
**.row.center**: riga centrata  
**.col-{n}**: definisce una colonna di dimensione {n}  
**.col-{n}.right**: fa flottare la colonna sulla destra  
**.col-{n}.pad**: utilizza il padding impostato nella griglia  
**.push-{n}**: sposta la colonna di una misura {n} (viene applicato specchiato per le colonne flottanti a destra)  
**.center**: centra una riga o una colonna (elimina il float)  
**.clearfix**: da applicare ai contenitori di elementi flottanti per correggere il dimensionamento  


Il codice html per utilizzare la griglia è del tipo:

    <div class="row {class}">
        <div class="col-{n}">
            {n} Rappresenta la grandezza della colonna, da 1 a n, in base a quante colonne sono impostate in {class}
        </div>
        <div class="col-{n} push-{m}">
            Qui la colonna è spostata di {m} rispetto alla sua posizione normale
        </div>
    </div>