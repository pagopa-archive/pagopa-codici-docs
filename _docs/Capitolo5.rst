
|pagoPA_logo|

+---------------------------------------------------------------------------------------------------+
| **SPECIFICHE ATTUATIVE DEI CODICI IDENTIFICATIVI DI VERSAMENTO, RIVERSAMENTO E RENDICONTAZIONE**  |
|                                                                                                   |
|                                                                                                   |
| *Allegato A alle "Linee guida per l'effettuazione dei pagamenti elettronici a favore delle*       |
| *pubbliche amministrazioni e dei gestori di pubblici servizi"*                                    |
|                                                                                                   |
|                                                                                                   |
| **Versione 1.3.1 - gennaio 2018**                                                                 |
+---------------------------------------------------------------------------------------------------+

.. _Riconciliazione del pagamento:

5. Riconciliazione del pagamento
================================

I pagamenti che non siano oggetto di un riversamento cumulativo da parte
del prestatore di servizi di pagamento dell’utilizzatore finale saranno
riconciliate con le informazioni memorizzate presso l’Ente Creditore
nella fase 2 (generazione del pagamento) del ciclo di vita del pagamento
(vedi pagina 9): infatti, analizzando la stringa contenuta nella causale
del versamento che l’istituto tesoriere/cassiere fornisce all’Ente
Creditore [8]_, sarà possibile riscontrare la correttezza del pagamento
attraverso il componente **<IUV>** della causale e generare in modo
automatico la reversale di incasso e la quietanza di pagamento (quando
previste).

.. _specificità-per-il-pagamento-della-marca-da-bollo-digitale:

5.1 Specificità per il pagamento della Marca da bollo digitale
--------------------------------------------------------------

Con riferimento al documento “Bollo Telematico @e.bollo - Linee guida
per pubbliche amministrazioni e prestatori di servizi di
pagamento” [9]_ emanato di concerto tra l’Agenzia delle Entrate e
l’Agenzia per l’Italia Digitale, si rammenta che nel processo di
acquisto della marca da bollo digitale non vi è alcun accredito all’Ente
Creditore al quale deve essere consegnata l’istanza o che emette l’atto
o il documento in bollo: infatti l’utilizzatore finale ottiene la marca
da bollo digitale direttamente dal PSP concessionario del servizio, il
quale la aveva preventivamente acquisita dall’Agenzia delle Entrate.

Pertanto il processo di riconciliazione deve escludere i pagamenti
relativi all’acquisto della Marca da bollo digitale.


.. [8]
   Ad esempio attraverso i flussi automatizzati dell’ordinativo informatico.

.. [9]
   ex art. 6, comma 2, provvedimento del Direttore dell’Agenzia delle Entrate del 19 settembre 2014.


.. |pagoPA_logo| image:: media/header.png
   
