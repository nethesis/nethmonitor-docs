.. index::
   single: Wizard

.. _wizard-section:

========
|wizard|
========


Introduzione
============

Il :dfn:`|wizard|` è un'interfaccia completamente sviluppata da Nethesis con l'intento di soddisfare 
due specifiche esigenze:

* arrichire le funzionalità del modulo di monitoraggio, |adagios|;
* consentire il colloquio tra |ocs|, il modulo deputato all'invntario degli asset IT, e la parte di monitoraggio.

**Funzionalità:**

Attraverso il modulo :index:`|wizard|` è possibile:

* definire e gestire il monitoraggio di host in index:`modalità passiva`;
* installare e gestire le :dfn:`sonde hardware` |probe|;
* definire nuovi servizi e classi di servizio per arrichire i monitoraggio passivo e tramite sonda;
* definire gli host da monitorare a partire dai dispositivi presenti lasita degli asset inventariati.


Accesso
=======

Per accedere all':dfn:`interfaccia web` del |wizard| è sufficiente utilizzarel'apposito link presente nella sezione 
nella barra degli strumenti di |adagios|.
E' altrimenti possibile accedere direttamente all'applicativo digitando nella barra degli indirizzi ``https://a.b.c.d/nethmonitor`` 
oppure ``https://server/adagios`` dove *a.b.c.d* e *server* sono rispettivamente l'indirizzo IP ed il nome del server 
impostati in fase di installazione.


|parent_product| utilizza certificati SSL auto-firmati, sarà quindi necessario
accettare esplicitamente tali certificati la prima volta che si accede al server.
La connessione è comunque sicura e cifrata.

Login
-----

Per accedere all'interfaccia è necessario utilizzare le credenziali di ``admin`` che, di default,
non sono attive.
Per attivare l'utente seguire le indicazioni riportate in `questa pagina <http://nethserver.docs.nethesis.it/it/latest/accounts.html#admin-user-section>`_ del manuale di |parent_product|.
