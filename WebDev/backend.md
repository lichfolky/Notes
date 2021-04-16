In ogni caso queste sono le funzioni che devono essere integrate all'interno di un client API
✔️ Gestione del token di autenticazione
✔️ Esposizione degli stati "fetching" ed "error" - Il FE deve sapere quando sta attendendo una risposta
✔️ Gestione centralizzata degli errori - In caso di 500 il client deve essere autonomo nel sollevare un'eccezione, tipo far vedere un banner
✔️ Auto logging degli errori ed invio ad un servizio dedicato (Sentry?)
✔️ Possibilità di persistere i dati all'interno del client così non devo portarmeli dietro all'interno dell'applicazione
✔️ Gestione degli headers customizzata per il BE
✔️ Possibilità di passare facilmente parametri in QueryString e in UrlPath senza dover concatenare le stringhe
✔️ Possibilità di essere concatenato con altri client per fare richieste in parallelo
