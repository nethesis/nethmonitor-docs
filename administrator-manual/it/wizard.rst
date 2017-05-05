.. index::
   single: Wizard

.. _wizard-section:

Wizard
======


Introduzione al Wizard
----------------------

Il :dfn:`Wizard` è un'interfaccia completamente sviluppata da Nethesis con l'intento di soddisfare 
due specifiche esigenze:

* arrichire le funzionalità del modulo di monitoraggio, Adagios;
* consentire il colloquio tra OCS Inventory, il modulo deputato all'invntario degli asset IT, e la 
  parte di monitoraggio.

**Caratteristiche principali:**

Attraverso il modulo :index:`Wizard` è possibile:

* definire e gestire il monitoraggio di host in index:`modalità passiva`;
* installare e gestire le :dfn:`sonde remote Curiosity`;
* definire nuovi servizi e classi di servizio per arrichire i monitoraggio passivo e tramite sonda;
* definire gli host da monitorare a partire dai dispositivi presenti lasita degli asset inventariati.


Accesso
-------

Per accedere all':dfn:`interfaccia web` del :index:`Wizard` è sufficiente utilizzare l'apposito link 
presente nella barra degli strumenti di :dfn:`Adagios`. E' altrimenti possibile accedere direttamente 
all'applicativo digitando nella barra degli indirizzi ``https://a.b.c.d/nethmonitor`` oppure 
``https://server/nethmonitor`` dove *a.b.c.d* e *server* sono rispettivamente l'indirizzo IP ed il nome 
del server impostati in fase di installazione.

|parent_product| utilizza certificati SSL auto-firmati, sarà quindi necessario accettare esplicitamente 
tali certificati la prima volta che si accede al server.
La connessione è comunque sicura e cifrata.

Login
^^^^^

Per accedere all'interfaccia è necessario utilizzare le credenziali di ``admin`` che, di default,
non sono attive.
Per attivare l'utente seguire le indicazioni riportate in `questa pagina <http://nethserver.docs.nethesis.it/it/latest/accounts.html#admin-user-section>`_ del manuale di |parent_product|.


Funzionalità
------------

Sistemi
^^^^^^^

La pagina :dfn:`Sistemi` consente di definire e gestire i nodi monitorabili in :dfn:`modalità passiva agentfull` 
o tramite una :dfn:`sonda remote Cusiosity`.


Nuovo sistema
~~~~~~~~~~~~~

Il menu :dfn:`Nuovo sistema` consente l'inserimento di un nuovo host da sottoporre a monitoraggio passivo/remoto.
L'interfaccia consente di selezionare un host tra quelli inventariati tramite :ref:`ocs-section`, attraverso 
un menu a tendina dedicato: scegliendo un host tra quelli inventariati il sistema si occuperà di compilare 
tutti i campi relativi alla sua configurazione di rete.
Alternativamente è possibile fornire manualmente i parametri dell'host da sottoporre a monitoraggio.

.. warning:: In caso di inserimento manuale dei dati è necessario ricordarsi di **evitare l'utilizzo di spazi vuoti**
             nel campo :dfn:`Nome sistema`.

Particolare attenzione va posta nella definizione del parametro ":dfn:`Genitore`" il sistema crea una 
:index:`relazione gerarchica` nella gestione degli allarmi relativi l'host configurato e l'apparato definito 
come suo genitore.
Se il genitore diventa irragiungibile, lo stato dell'host ad esso collegato viene automaticamente posto in uno 
stato :dfn:`Unknown`: questo accade proprio in virtù della relazione gerarchica stabilita.
Si pensi ad esempio ad un server collegato ad uno switch: nel momento in cui lo switch non è più raggiungibile 
non è possibile nemmeno stabilire lo stato dei servizi del server ad esso collegato.

.. note:: Nel caso specifico in cui un host sia monitorato tramite una :index:`sonda remota`, essa **dovrà** essere
          impescindibilmente definita come il :index`genitore` del nodo monitorato tramite essa.

L'interfaccia consente poi di specificare :index:`tipologia di monitoraggio` e relative :index:`classi di servizio` 
per abilitare i controlli desiderati sugli host monitorati.


Visualizza lista
~~~~~~~~~~~~~~~~

Consente di esplorare e gestire gli host monitorati passivamente o tramite sonda remota.
Da questa pagina è possibile eseguire il download dei pacchetti dell'':index:`agent software` per il monitoraggio 
passivo degli host.


Classi di servizi
^^^^^^^^^^^^^^^^^

L'interfaccia :dfn:`Classi di servizi` consente di gestire le classi di monitoraggio passivo e remoto predefinite 
e di crearne di personalizzate.


Servizi
^^^^^^^

L'interfaccia :dfn:`Servizi` consente di gestire i servizi di monitoraggio passivo e remoto predefiniti e di crearne 
di personalizzati.


Sonde
^^^^^

Il menu :dfn:`Sonde` consente di gestire le sonde remote collegate al |product| come illustrato nella sezione 
:ref:`probe-activation` contenuta nella pagina :ref:`probe-section`.

Le nuove sonde collegate ad un |product| vengono elencate in questa pagina.

Sono di default :dfn:`disabilitate` e vanno attivate tramite la :dfn:`check box` presente nel campo ":dfn:`Attivo?`".

Attraverso le icone presenti del campo ":dfn:`Azioni`" è invece possibile:

* modificare i parametri della sonda;
* visualizzare la :dfn:`lista dei messaggi` che |product| e sonda si scambiano.


Autodiscovery
^^^^^^^^^^^^^

Attraverso questa maschera è possibile pilotare la :index:`autodiscovery` della rete delle sonde remote: 
selezionando la sonda da utilizzare ed inserendo gli attributi della rete da analizzare, Curiosity eseguirà 
un nmap della network indicata restituendone gli host rilevati, permettendone un facile inserimento tra i 
nodi monitorati.

.. note:: l'autodiscocovery presente in questa maschera è utilizzabile unicamente per pilotare la scansione della rete tramite sonde remote.
          Per eseguire la scansione della rete locale in cui è inserito |product| andrà utilizzata la feature messa a disposizione dal modulo
          :ref:`okconfig-section`.


.. _servnethmon-section:

Server Nethmonitor
^^^^^^^^^^^^^^^^^^

Notifiche
~~~~~~~~~

In questa sezione è possibile specificare l':dfn:`indirizzo e-mail` a cui il sistema invierà i messaggi 
di allarme relativi ad host e servizi.
Questo parametro è modificabile anche dall'interfaccia di :ref:`status-section` di :ref:`adagios-section`.

Comandi
~~~~~~~

In questo menu sono presenti dei comandi per la gestione dei :index:`file di configurazione` e dei servizi 
del core di :index:`Nagios`.

