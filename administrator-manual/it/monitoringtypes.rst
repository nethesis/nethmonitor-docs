.. index::
   single: tipi di monitoraggio

.. _activemonitoring-section
.. _passivemonitoring-section

==============================
Monitoraggio tramite |product|
==============================

Esistono due principali tipi di monitoraggio degli host implementabili attraverso |product|: quello in :dfn:`modalità attiva` 
e quello in :dfn:`modalità passiva`.
Entrambi prevedono l'installazione presso l'host monitorato di un software detto agent.

Monitoraggio attivo
===================

Nella *modalità attiva* è il server |product| che si collega all'host monitorato per eseguire i controlli.
Tale modalità è la più affidabile ed è consigliata per gli host nella rete locale.
I controlli di tipo attivo possono essere effettuati in due modalità:

* con una interrogazione diretta server/client (:dfn:`modalità agentless`);
* attraverso l'adozione di un agent software da installare lato client (:dfn:`modalità agentfull`).

La modalità attiva funziona correttamente se sono rispettate le seguenti condizioni:

* l'host monitorato consente connessioni sulla porta TCP 5666,
* tra il NethMonitor e l'host la connettività è stabile. 
