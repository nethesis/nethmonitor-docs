.. index::
   single: Sonde
   single: Curiosity

.. _probe-section:

======================
Sonde hardware |probe|
======================


Introduzione
============

Le :dfn:`sonde remote |probe|` sono la soluzione ideale per gestire in modo semplice ed efficace il 
monitoraggio di host remoti localizzati in sedi periferiche.
Si tratta di veri e propri appliance autoconfiguranti che collegati ad una rete dotata di 
server DHCP sono in grado di recepire un indirizzo e mettersi in comunicazione con il |product| 
a cui vengono correlate, fungendo da veri e propri proxy di monitoraggio: una volta accese, le 
sonde possono scansionare la rete in cui vengono inserite, restituendo al |product| il 
risultato dell'attività di discovery.
Attraverso l'interfaccia |wizard| è possibile inviare alla sonda le configurazioni di monitoraggio 
predisposte centralmente per abilitare il controllo dei nodi della rete remota.

.. note:: Le sonde |probe| sono in grado di gestire unicamente controlli di tipo attivo agentless


Abilitazione sonde
==================

Per poter essere utilizzate, le :index:`sonde remote |probe|` necessitano di essere attivate e collegate
ad una istanza di |product| attraverso una semplice procedura di abilitazione.
Ad ogni sonda è associato un :dfn:`hash` univoco
