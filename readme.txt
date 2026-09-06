Web server, a cosa serve in generale

Il sito non è un semplice file di testo: index.html deve andare a chiedere i contenuti al file data.json e alle immagini in pages/, 
attraverso un comando chiamato fetch. 

I browser permettono questo tipo di richiesta solo se la pagina è raggiunta con un indirizzo 
che comincia per http:// (o https://). 

Se apri il file con doppio click, l'indirizzo comincia per file://, e il browser blocca la richiesta 
per sicurezza — per questo vedevi solo la struttura vuota, senza testi né immagini.

Un "server locale" (Python o Live Server) non fa altro che questo: prende i file della cartella e li rende disponibili tramite un vero 
indirizzo http://, così il browser smette di bloccare tutto.

Perché Windows mostra un popup di sicurezza

Per fare questo, il programma deve aprire una "porta" — un canale numerato (8000, 5500...) su cui resta in ascolto, pronto a rispondere. 
Windows Defender nota ogni volta che un nuovo programma prova ad aprire una porta per la prima volta, e chiede conferma. 
Non è un allarme sul progetto: è un controllo che scatta sul programma (Python, Live Server), non sul sito che stai costruendo.

È sicuro approvarlo per "rete privata": il server risponde solo a richieste che partono dal tuo stesso computer (localhost), 
quindi nessuno da fuori può raggiungerlo per caso.

Perché un comando ha funzionato e l'altro no

Qui non c'entra la sicurezza, è solo una questione di nome: su questo PC Windows, Python è registrato come python, non come python3. 
Quando scrivi python3 Windows non trova nulla con quel nome esatto e ti reindirizza (in modo poco chiaro) verso lo Store. 
Con python -m http.server 8000 invece funziona, come hai visto tu stesso nei log con tutte le pagine caricate correttamente (righe con 200).

In una frase

Il server serve per far parlare correttamente il browser con i file del progetto; il popup di Windows è un controllo di routine 
sul programma che apre quella comunicazione, non un rischio; e l'unico intoppo che hai avuto (python3 vs python) era solo un nome di comando 
sbagliato per questo PC.
