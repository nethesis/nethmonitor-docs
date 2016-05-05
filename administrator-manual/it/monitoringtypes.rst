.. index::
   single: Tipi di monitoraggio

.. _monitoringtype-section:

Monitoraggio tramite |product|
==============================

Esistono due principali tipi di monitoraggio degli host implementabili attraverso |product|: quello in :dfn:`modalità attiva` 
e quello in :dfn:`modalità passiva`.
Entrambi prevedono l'installazione sull'host monitorato di un software detto :dfn:`agent` ma il monitoraggio attivo consente
in alcuni casi di poter effettuare dei controlli senza la necessità di installare alcun software (:dfn:`modalità agentless`).

.. _activemonitoring-section:

Monitoraggio attivo
-------------------

Nella :index:`modalità attiva` è il server |product| che si collega all'host monitorato per eseguire i controlli.
Tale modalità è la più affidabile ed è consigliata per gli host nella rete locale.
I controlli di tipo attivo possono essere effettuati in due modalità:

* con una interrogazione diretta server/client (:index:`modalità agentless`);
* attraverso l'adozione di un agent software da installare lato client (:dfn:`modalità agentfull`).

Il monitraggio *attivo* di tipo *agentless* non prevede l'installazione di software sull'host monitorato: è |product| che contatta 
l'host monitorato, è perciò indispensabile sincerarsi che:

* il nodo controllato sia raggiungibile da |product|;
* il nodo controllato sia correttamente  configurato per esporre il dato oggetto del monitoraggio.

In questa modalità, però, molti tipi di controllo potrebbero non essere possibili.
In generale, questo tipo di monitoraggio è utilizzato per controllare la raggiungibilità di host *diskless* come:

* Firewall
* Router
* Stampanti
* Switch 

La modalità :index:`attiva agentfull` prevede l'adozione sull'host monitorato di un :index:`agent`, un software che fa da tramite 
nelle comunicazioni tra l'host ed il |product|: il server si collega all'host monitorato e chiede all'agent di eseguire i controlli 
e di inviargli i risultati.
Tale modalità è la più affidabile ed è consigliata per gli host nella rete locale. 
La modalità attiva funziona correttamente se sono rispettate le seguenti condizioni:

* l'host monitorato consente connessioni sulla porta TCP **5666**;
* tra il NethMonitor e l'host la connettività è stabile.

.. note:: Tutti gli host monitorati attivamente devono essere raggiungibili dal server NethMonitor alla porta TCP **5666**


.. _passivemonitoring-section:

Monitoraggio passivo
--------------------

Nella :index:`modalità passiva` l'agent installato sull'host monitorato raccoglie autonomamamente dati sullo stato della macchina e dei servizi ed
ad intervalli regolari invia i dati raccolti a |product|.

.. note:: Il monitoring passivo è possibile unicamente in versione agentfull!

La modalità passiva è consigliata per gli host remoti.
La modalità passiva funziona correttamente se sono rispettate le seguenti condizioni:

* il client può contattare il server sull'IP o nome pubblico sulla porta TCP **5667**;
* il server è in grado di ricevere connessioni sulla porta TCP **5667**, pertanto, se necessario, controllare i port forward. 

.. note:: Tutti gli host monitorati passivamente devono essere in grado di raggiungere l'IP pubblico del server NethMonitor alla porta TCP **5667**

