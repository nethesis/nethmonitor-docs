.. index::
   single: Adagios

.. _adagios-section:

Adagios
=======

Introduzione ad Adagios
-----------------------

`Adagios <http://adagios.org/>`_ è un'interfaccia di configurazione web based per :index:`|core|`
costruita per essere semplice ed intuitiva, al fine di nascondere buona parte della complessità di
Nagios "sotto al cofano".
:index:`Adagios` fornisce un'interfaccia di status e management molto completa del tutto alternativa 
a quella nativa di Nagios e mette a disposizione molteplici interfacce rest per l'accesso ai dati 
di status e di configurazione degli host monitorati.
L'interfaccia di Adagios funge da collettore per le informazioni di monitoraggio, consentendo di 
visualizzare e gestire in modo semplice ed intuitivo gli host monitorati.
Attraverso Adagios è possibile definire tutti controlli di tipo :index:`*attivo*` (per approfondimenti 
si rimanda alla sezione :ref:`activemonitoring-section`).


**Caratteristiche principali:**

* completa interfaccia di visualizzazione/modifica per host,servizi,etc
* numerosi template di configurazione e plugin in bundle
* autodiscovery di rete
* installazione remota di agent linux/windows
* interfaccia di visualizzazione di Status moderna ed intuitiva
* backup dei dati di Adagios integrato nella procedura di backup di |parent_product|
* interfacce rest per lo status di host e servizi e per visualizzazione/modifica della configurazione
* auditing completo di tutti i cambiamenti effettuati


Accesso
-------

Per accedere all':dfn:`interfaccia web` di Adagios è sufficiente utilizzare il link presente nella sezione *Applicazioni* 
della *Dashboard* di |parent_product|.
E' altrimenti possibile accedere direttamente all'applicativo senza passare per il *server-manager* digitando nella barra 
degli indirizzi ``https://a.b.c.d/adagios`` oppure ``https://server/adagios`` dove *a.b.c.d* e *server* sono 
rispettivamente l'indirizzo IP ed il nome del server impostati in fase di installazione.


Il Server Manager utilizza certificati SSL auto-firmati, sarà quindi necessario
accettare esplicitamente tali certificati la prima volta che si accede al server.
La connessione è comunque sicura e cifrata.

Login
^^^^^

Per accedere all'interfaccia è necessario utilizzare le credenziali di ``admin`` che, di default, 
non sono attive.
Per attivare l'utente seguire le indicazioni riportate in `questa pagina <http://nethserver.docs.nethesis.it/it/latest/accounts.html#admin-user-section>`_ del manuale di |parent_product|.


Funzionalità
------------

.. _status-section:

Status
^^^^^^

L'interfaccia di :dfn:`Status` di |product| mette a disposizione numerosi sinottici e report utili a rilevare
e gestire gli allarmi attivi sui nodi controllati.
Le varie visualizzazioni preconfigurate nella pagina di :index:`Status` consentono di consultare le informazioni 
a livello globale ma anche filtrandole in modo più puntuale in base agli host od ai servizi monitorati.


Status Overview / Open Problems / All Problems
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Attraverso quete sezioni il sistema fornisce in diverse rappresentazioni lo stato degli :index:`allarmi attivi` non gestiti.


Hosts / Services
~~~~~~~~~~~~~~~~

Questi sinottici mettono a disposizione una visualizzazione più approfonidita di :index:`host` e index:`servizi` monitorati,
consentendo di filtrarli con una potente funzione di :dfn:`ricerca globale`.


Contacts
~~~~~~~~

In questa sezione è possibile specificare l':dfn:`indirizzo e-mail` a cui il sistema invierà i messaggi di allarme relativi ad host e servizi.
Questo parametro è modificabile anche dall'interfaccia :ref:`servnethmon-section` del :ref:`wizard-section`.

Network Parents
~~~~~~~~~~~~~~~

Attraverso questa sezione è possibile definire una :index:`relazione gerarchica` tra i nodi monitorati attraverso |product|.
Definire un nodo come :index:`parent` di un altro conferisce interdipendenza nella gestione degli allarmi relativi all'host configurato 
ed all'apparato definito come suo genitore.
Se il genitore diventa irraggiungibile, lo stato dell'host ad esso collegato viene automaticamente posto in uno stato :dfn:`Unknown`:
questo accade proprio in virtù della relazione gerarchica stabilita.
Si pensi ad esempio ad un server collegato ad uno switch: nel momento in cui lo switch non è più raggiungibile non è possibile nemmeno 
stabilire lo stato dei servizi del server ad esso collegato.

.. _okconfig-section:

Okconfig
^^^^^^^^

Il vero cuore di Adagios, :dfn:`Okconfig` è un potente motore di configurazione di host e servizi.
:index:`Okconfig` mette a disposizione un corposo numero di :dfn:`template di configurazione` già pronti all'utilizzo 
per implementare il monitoraggio in modalità :dfn:`attiva` dei dispositivi.
*Okconfig* permette inoltre di effettuare una scansione dei dispositivi presenti in rete attraverso la funzione di 
:index:`autodiscovery` che consente di sottoporre agevolmente nuovi host al monitoraggio.
Inoltre, il modulo consente di generare ed effettuare l'installazione remota degli :index:`agent software` necessari 
per il monitoring dei sistemi più evoluti.
L'estrema flessibilità del modulo consente poi una agevole customizzazione dei tempalte di monitoraggio (`si veda qui <https://github.com/opinkerfi/adagios/wiki/Customising-okconfig-templates-to-your-needs>`_).

Configure
^^^^^^^^^

Dal menu :dfn:`Configure` è possibile accedere ai vari aspetti del sistema più a basso livello: il pannello 
consente di intervenire direttamente sui file di configurazione e tempalte che defibniscono host, servizi e 
check command di monitoraggio.

.. warning:: Le modifiche effettuate attraverso questo pannello si ripercuotono trasveralmente su tutto l'ambiente
             di monitoraggio: è necessario porcedere con estrema cautela per evitare di provocare malfunzionamenti
             imprevisti.


Nagios
^^^^^^

Il menu :dfn:`Nagios` consente di accedere all'interfaccia nativa del core di Adagios.


Wizard
^^^^^^

Il menu :dfn:`Wizard` permette di accedere all'interfaccia del modulo :ref:`wizard-section`.

.. _multisite-section:

Multisite
---------

Adagios supporta la connessione a più backend allo scopo di mostrare più istanze di Nagios in un'unica interfaccia web. 
Questo tipo di interfacciamento vale unicamente per le connessioni :dnf:`livestatus`, quindi solo per la visualizzazione 
e la raccolta dati, non per la configurazione e la modifica di oggetti.

.. warning:: Al momento la feature è sperimentale.


Connessione ad una o più istanze remote
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Adagios utilizza la variabile di configurazione *livestatus_path* per contattare il socket livestatus di una istanza remota.
Se *livestatus_path* non viene fornito, Adagios adotta automaticamente le configurazioen contenute nel file *nagios.cfg*.

.. note:: Di default Adagios utilizza la porta **6557** per le comunicazioni livestatus è perciò necessario sincerarsi che
          i backend remoti siano raggiungibili su quella porta.

Per indicare esplicitamente ad Adagios quali istanze remote contattare sarà sufficiente inserire un elenco separato da virgole
nel campo "*Livestatus path*" presente nel menu impostazioni dell'intefraccia web, raggiungibile cliccado sull'icona a forma
di ingranaggio presente in alto a destra e scegliendo la voce :dfn:`Settings`.
Se ad esempio si volesse contattare le istanze di Adagios attive sui server *remoteserver.example.com* e *remoteserver2.example.com*
la sintassi da utilizzare per valorizzare il campo :index:`Livestatus path` sarà la seguente: ::

    /var/spool/nagios/cmd/livestatus,remoteserver.example.com:6557,remoteserver2.example.com:6557

Una volta impelmentata la configurazione, nella barra di Adagios verrà attivata una nuova icona attraverso la quale sarà possibile
abilitare e disabilitare con estrema facilità la visualizzazione degli host afferenti ai backend remoti.

