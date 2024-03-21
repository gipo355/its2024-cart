Esercizio

creare un componente per la singola card

    prodotto in input, un output per il click su add e uno per il click su details
    internamente calcola il prezzo effettivo considerando sconto e iva

gestire la logica per l'aggiunta di un componente al carrello quando si fa click su add
creare un componente per il carrello da visualizzare lateralmente

    visualizza il prezzo totale in alto
    subito sotto un pulsante per andare alla pagina /checkout
    ancora sotto la lista degli articoli aggiunti con il pulsante per rimuoverli

    creare una pagina di dettaglio del prodotto
        navigare alla pagina quando si fa click su details
        nella pagina è sempre visibile il carrello lateralmente
        in una sezione della pagina sarà possibile andare a selezionare la quantità e aggiungere al carrello

Product-card

Specifiche:

    prende un prodotto come input
    calcola il prezzo compreso di sconto e iva
    ha un output (add) per quando l'utente decide di aggiungere un prodotto al carrello
    ha un output (detail) per quanto l'utente decide di andare alla pagina di dettaglio
    mostra un errore quando la quantità è minore di 1 e disabilita il pulsante

side-cart

E' presente lateralmente sia nella pagina di ricerca sia in quella di dettaglio di un prodotto

Specifiche:

    prende automaticamente i dati da CartSourceService
    mostra in alto il totale da pagare (quindi compreso di tutti i calcoli)
    mostra il pulsante checkout che porta alla pagina di checkout

    mostra la lista degli articoli presenti nel carrello con
        nome
        quantità non modificabile
        prezzo totale
        pulsante per rimuovere l'elemento dal carrello
    da sviluppare come smart-component, non riceve input dalla pagina
    viene nascosto automaticamente se il carrello è vuoto (questa logica va gestita esternamente al componente)

product-detail

Specifiche:

    è un componente di pagina sotto la rotta /products/:id

    mostra:
        una finta immagine sulla sinistra (se volete andate a modificare le api e tornate anche l'url di una immagine, faker ha i metodi per generarli)
        il nome del prodotto
        il prezzo e lo sconto
        l'input con la quanità e il pulsante add
        la descrizione
        un link per tornare alla ricerca
    l'input deve mostrare un errore se invalido (minore di 1) e il pulsante si deve disabilitare
    se riuscite fate in modo che il prodotto venga mandato tramite un resolver

Cose che non abbiamo visto da cercare

    come creare la rotta /products/:id e andare a prendere il parametro id da un component o da un resolver
    come aggiungere link alle rotte (vedere routerLink)
    come applicare dinamicamente classi a un tag nel template. Questo ci serve per usare le classi di bootstrap per la validazione
    come abilitare e disabilitare un elemento
    come combinare più observable. Questo servirà nel carrello laterale dove abbiamo sia gli elmenti che l'iva e dobbiamo fare i calcoli. Vedere il metodo combineLatest di rxjs
