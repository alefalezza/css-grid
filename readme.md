# Css grid framework

Framework per la generazione di griglie css realizzato in [less.css](http://lesscss.org/).

Il framework espone una sola funzione ".make-grid" che può essere utilizzata più volte per generare più griglie con proprietà diverse in un solo css.
Ogni griglia è contraddistinta da una classe che funge da namespace e permette di utilizzare più di una griglia per pagina.
Per ciascuna griglia è possibile personalizzare il numero di colonne e la spaziatura. La larghezza delle colonne è definita in percentuale, il che permette di realizzare riche con larghezze diverse e griglie annidate.

## Utilizzo:

    .make-grid( class{string}, colonne{int}, @breakopint{px}, margin{%}, padding{% | px} );

### Parametri:

- class: stringa che identifica la classe della riga
- colonne: intero, è il numero di colonne per la riga con classe .row.@class
- breakpoint: rappresenta il valore della larghezza dello schermo in px, al di sotto del quale le colonne vengono impilate (versione mobile) 
- margin: se vuoi che le colonne abbiano un margin, impostalo qui (in percentuale!!). Default 0
- padding: se vuoi che le colonne abbiano un padding, impostalo qui. Default 0

### Genera le seguenti classi:

**.row**: definisce una riga  
**.row.center**: riga centrata  
**.col-{n}**: definisce una colonna di dimensione {n}  
**.col-{n}.right**: fa flottare la colonna sulla destra  
**.col-{n}.pad**: utilizza il padding impostato nella griglia  
**.push-{n}**: sposta la colonna di una misura {n} (viene applicato specchiato per le colonne flottanti a destra)  
**.center**: centra una riga o una colonna (elimina il float)  
**.clearfix**: da applicare ai contenitori di elementi flottanti per correggere il dimensionamento  

### Html

Il codice html per utilizzare la griglia è del tipo:

    <div class="row {class}">
        <div class="col-{n}">
            {n} Rappresenta la grandezza della colonna, da 1 a n, in base a quante colonne sono impostate in {class}
        </div>
        <div class="col-{n} push-{m}">
            Qui la colonna è spostata di {m} rispetto alla sua posizione normale
        </div>
    </div>