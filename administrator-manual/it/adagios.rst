.. index::
   single: Adagios

.. _adagios-section:

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
L'interfaccia di |adagios| funge da collettore per le informazioni di monitoraggio, consentendo di 
visualizzare e gestire in modo semplice ed intuitivo gli host monitorati.
Attraverso |adagios| è possibile definire tutti controlli di tipo :index:`*attivo*` (per approfondimenti 
si rimanda alla sezione :ref:`activemonitoring-section`).


**Caratteristiche principali:**

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

Per accedere all':dfn:`interfaccia web` di |adagios| è sufficiente utilizzare il link presente nella sezione *Applicazioni* 
della *Dashboard* di |parent_product|.
E' altrimenti possibile accedere direttamente all'applicativo senza passare per il *server-manager* digitando nella barra
degli indirizzi ``https://a.b.c.d/adagios`` oppure ``https://server/adagios`` dove *a.b.c.d* e *server* sono 
rispettivamente l'indirizzo IP ed il nome del server impostati in fase di installazione.


Il Server Manager utilizza certificati SSL auto-firmati, sarà quindi necessario
accettare esplicitamente tali certificati la prima volta che si accede al server.
La connessione è comunque sicura e cifrata.

Login
-----

Per accedere all'interfaccia è necessario utilizzare le credenziali di ``admin`` che, di default, 
non sono attive.
Per attivare l'utente seguire le indicazioni riportate in `questa pagina <http://nethserver.docs.nethesis.it/it/latest/accounts.html#admin-user-section>`_ del manuale di |parent_product|.


Funzionalità
============

Status
------

L'interfaccia di :dfn:`Status` di |product| mette a disposizione numerosi sinottici e report utili a rilevare
e gestire gli allarmi attivi sui nodi controllati.
Le varie visualizzazioni preconfigurate nella pagina di :index:`Status` consentono di consultare le informazioni 
a livello globale ma anche filtrandole in modo più puntuale in base agli host od ai servizi monitorati.

Okconfig
--------

Il vero cuore di |adagios|, :dfn:`Okconfig` è un potente motore di configurazione di host e servizi.
index:`Okconfig` mette a disposizione un corposo numero di :dfn:`template di configurazione` già pronti all'utilizzo 
per implementare il monitoraggio in modalità :dfn:`attiva` dei dispositivi.
*Okconfig* permette inoltre di effettuare una scansione dei dispositivi presenti in rete attraverso la funzione di 
:index:`autodiscovery` che consente di sottoporre agevolmente nuovi host al monitoraggio.
Inoltre, il modulo consente di generare ed effettuare l'installazione remota degli :index:`agent software` necessari 
per il monitoring dei sistemi più evoluti.
L'estrema flessibilità del modulo consente poi una agevole customizzazione dei tempalte di monitoraggio (`si veda qui <https://github.com/opinkerfi/adagios/wiki/Customising-okconfig-templates-to-your-needs>`).

Configure
---------

Dal menu :dfn:`Configure` è possibile accedere ai vari aspetti del sistema più a basso livello: il pannello 
consente di intervenire direttamente sui file di configurazione e tempalte che defibniscono host, servizi e 
check command di monitoraggio.

.. warning:: Le modifiche effettuate attraverso questo pannello si ripercuotono trasveralmente su tutto l'ambiente
             di monitoraggio: è necessario porcedere con estrema cautela per evitare di provocare malfunzionamenti
             imprevisti.


Nagios
------

Il menu :dfn:`Nagios` consente di accedere all'interfaccia nativa del core di |adagios|.


Wizard
------

Il menu :dfn:`Wizard` permette di accedere all'interfaccia del modulo :ref:`wizard-section`.

