.. index::
   single: adagios

.. _accesso-section:

=========
|adagios|
=========


Introduzione
============


`|adagios| <http://adagios.org/>`_ è un'interfaccia di configurazione web based per :index:`|core|`
costruita per essere semplice ed intuitiva, al fine di nascondere buona parte della complessità di
Nagios "sotto al cofano".
:index:`|adagios|` fornisce un'interfaccia di status e management molto completa del tutto alternativa 
a quella nativa di Nagios e mette a disposizione molteplici interfacce rest per l'accesso ai dati 
di status e di configurazione degli host monitorati.


**Funzionalità:**

* completa interfaccia di visualizzazione/modifica per host,servizi,etc
* numerosi template di configurazione e plugin in bundle
* autodiscovery di rete
* installazione remota di agent linux/windows
* interfaccia di visualizzazione di Status moderna ed intuitiva
* backup dei dati di Adagios integrato nella procedura di backup di |parent_product|
* interfacce rest per lo status di host e servizi e per visualizzzione/modifica della configurazione
* auditing completo di tutti i cambiamenti effettuati


Accesso
=======

Per accedere all':dfn:`interfaccia web` |adagios| digitando nella barra degli indirizzi 
``https://a.b.c.d/adagios`` oppure ``https://server/adagios`` dove *a.b.c.d* e *server* sono rispettivamente
l'indirizzo IP ed il nome del server impostati in fase di installazione..


Il Server Manager utilizza certificati SSL auto-firmati, sarà quindi necessario
accettare esplicitamente tali certificati la prima volta che si accede al server.
La connessione è comunque sicura e cifrata.

Login
-----

Per accedere all'interfaccia è necessario utilizzare le credenziali di ``admin`` che, di default, 
non sono attive.
Per attivare l'utente seguire le indicazioni riportate in `questa pagina <http://nethserver.docs.nethesis.it/it/latest/accounts.html#admin-user-section>`_ del manuale di |parent_product|.
