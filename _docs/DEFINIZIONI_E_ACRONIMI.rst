
|pagoPA_logo|
   
+---------------------------------------------------------------------------------------------------+
| **SPECIFICHE ATTUATIVE DEI CODICI IDENTIFICATIVI DI VERSAMENTO, RIVERSAMENTO E RENDICONTAZIONE**  |
|                                                                                                   |
|                                                                                                   |
| *Allegato A alle "Linee guida per l'effettuazione dei pagamenti elettronici a favore delle*       |
| *pubbliche amministrazioni e dei gestori di pubblici servizi"*                                    |
|                                                                                                   |
|                                                                                                   |
| **Versione 1.4.0 - ottobre 2021**                                                                 |
+---------------------------------------------------------------------------------------------------+


Definizioni e Acronimi
======================

+-------------------------------+-----------------------------------------------------------------------------------+
| **Definizione / Acronimo**    | **Descrizione**                                                                   |
+-------------------------------+-----------------------------------------------------------------------------------+
| AgID                          | Ente istituito ai sensi del decreto                                               |
|                               | legge n. 83 del 22 giugno 2012 convertito                                         |
| Agenzia per l’Italia Digitale | con legge n. 134 del 7 agosto 2012 (già DigitPA).                                 |
|                               |                                                                                   |
|                               | Gestore del Nodo dei Pagamenti-SPC.                                               |
+-------------------------------+-----------------------------------------------------------------------------------+
| CAD                           | Codice dell'amministrazione digitale: decreto                                     |
|                               | legislativo 7 marzo 2005, n. 82 aggiornato con le modifiche e integrazioni.       |
+-------------------------------+-----------------------------------------------------------------------------------+
| Certificati SSL               | Documenti digitali da utilizzare con protocolli SSL                               |
|                               | (ovvero Secure Sockets Layer) che servono a certificare il titolare di un sito    |
|                               | web e trasmettere le informazioni in forma crittografata.                         |
+-------------------------------+-----------------------------------------------------------------------------------+
| Codice IUV                    | Sinonimo rafforzativo di IUV. È definito al                                       |
|                               | `paragrafo 7.1 delle Linee guida. <http://www.agid.gov.it/sites/default/files/    |
|                               | linee_guida/lineeguidapagamenti_v_1_1_0_0.pdf>`_                                  |
|                               |                                                                                   |
+-------------------------------+-----------------------------------------------------------------------------------+
| EC                            | Nel contesto del sistema pagoPA®                                                  |
|                               |  comprende                                                                        |
| Enti Creditori                | le pubbliche amministrazioni definite nell’articolo 2, comma 2 del CAD ed i       |
|                               | gestori di pubblici servizi “nei rapporti con l’utenza”. A prescindere dalla      |
|                               | natura giuridica, è il soggetto intestatario del conto di pagamento utilizzato    |
|                               | per l’accredito di cui all’operazione di pagamento elettronico eseguita           |
|                               | attraverso il Nodo dei Pagamenti-SPC.                                             |
+-------------------------------+-----------------------------------------------------------------------------------+
| EPC                           | European Payments Council (Consiglio europeo per i                                |
|                               | pagamenti) - sostiene e promuove la creazione della SEPA attraverso               |
|                               | l'autoregolamentazione dell’industria bancaria. EPC definisce le posizioni comuni |
|                               | per i servizi di pagamento di base all'interno di un mercato competitivo,         |
|                               | fornisce orientamenti strategici per la standardizzazione, formula le migliori    |
|                               | pratiche a supporto e controlla l'attuazione delle decisioni prese.               |
+-------------------------------+-----------------------------------------------------------------------------------+
| Flusso                        | Serie di dati oggetto di un processo di                                           |
|                               | elaborazione o trasmissione.                                                      |
+-------------------------------+-----------------------------------------------------------------------------------+
| Intermediario tecnologico     | EC o PSP aderente a pagoPA® che gestisce le attività di interconnessione al       |
|                               | NodoSPC per conto di altri soggetti aderenti a pagoPA® (PA o PSP), ai sensi del   |
|                               | `§ 8.3.3 delle Linee guida. <http://www.agid.gov.it/sites/default/files/          |
|                               | linee_guida/lineeguidapagamenti_v_1_1_0_0.pdf>`_                                  |
|                               |                                                                                   |
+-------------------------------+-----------------------------------------------------------------------------------+
| IPA                           | L'Indice delle Pubbliche Amministrazioni (IPA) costituisce l'archivio             |
|                               | ufficiale contenente i riferimenti organizzativi, telematici e toponomastici      |
|                               | delle pubbliche Amministrazioni.                                                  |
|                               |                                                                                   |
|                               | L'articolo 57-bis del CAD pone in capo alle Amministrazioni la responsabilità     |
|                               | dei dati pubblicati e il loro costante aggiornamento.                             |
+-------------------------------+-----------------------------------------------------------------------------------+
| Istituto tesoriere            | Soggetto finanziario affidatario del servizio di tesoreria o di cassa             |
|                               | della singola amministrazione, ivi compresa la Banca d’Italia.                    |
+-------------------------------+-----------------------------------------------------------------------------------+
| IUV                           | Acronimo di Identificativo Univoco Versamento.                                    |
+-------------------------------+-----------------------------------------------------------------------------------+
| Linee guida                   | Il documento “Linee guida per l'effettuazione dei pagamenti a favore delle        |
|                               | pubbliche amministrazioni e dei gestori di pubblici servizi” pubblicato           |
|                               | dall’Agenzia per l’Italia Digitale.                                               |
+-------------------------------+-----------------------------------------------------------------------------------+
| Nodo dei Pagamenti-SPC        | Piattaforma tecnologica per l’interconnessione e l’interoperabilità               |
|                               | tra le Pubbliche Amministrazioni e i Prestatori di Servizi di Pagamento           |
|                               | di cui all'articolo 5, comma 2 del CAD. Per le regole e le modalità di utilizzo   |
|                               | di detta piattaforma si rinvia al documento                                       |
|                               | “Specifiche attuative del Nodo dei Pagamenti-SPC”                                 |
|                               | pubblicato sul sito dell’Agenzia per l’Italia Digitale.                           |
+-------------------------------+-----------------------------------------------------------------------------------+
| PA                            | Pubblica Amministrazione (centrale e locale).                                     |
+-------------------------------+-----------------------------------------------------------------------------------+
| pagoPA:sup:'®'                | Il sistema dei pagamenti a favore delle pubbliche amministrazioni                 |
|                               | e dei gestori di pubblici servizi.                                                |
+-------------------------------+-----------------------------------------------------------------------------------+
| Partner tecnologico           | Soggetto che gestisce le attività di interconnessione al NodoSPC per conto        |
|                               | di una PA, nel rispetto delle specifiche tecniche contenute nelle Linee guida.    |
+-------------------------------+-----------------------------------------------------------------------------------+
| PSP                           | Prestatore di Servizi di Pagamento.                                               |
+-------------------------------+-----------------------------------------------------------------------------------+
| SACI                          | Specifiche attuative dei codici identificativi di versamento,                     |
|                               | riversamento e rendicontazione, Allegato A alle Linee guida.                      |
+-------------------------------+-----------------------------------------------------------------------------------+
| SANP                          | Specifiche attuative del Nodo dei Pagamenti-SPC, Allegato                         |
|                               | B alle Linee guida.                                                               |
+-------------------------------+-----------------------------------------------------------------------------------+
| SCT                           | SEPA Credit Transfer                                                              |
+-------------------------------+-----------------------------------------------------------------------------------+
| SEPA                          | Single Euro Payments Area (Area unica dei pagamenti in euro),                     |
|                               | ovvero un'area nella quale gli utilizzatori degli strumenti di                    |
|                               | pagamento - i cittadini, imprese, pubbliche amministrazioni e gli altri           |
|                               | operatori economici - indipendentemente dalla loro residenza, possono             |
|                               | effettuare e ricevere pagamenti in euro non in contanti sia all'interno dei       |
|                               | confini nazionali che fra paesi diversi, alle stesse condizioni e con gli         |
|                               | stessi diritti e obblighi. La SEPA riguarda 32 paesi (tutti i paesi dell'Unione   |
|                               | Europea più l'Islanda, la Norvegia, il Liechtenstein, la Svizzera e il            |
|                               | Principato di Monaco).                                                            |
+-------------------------------+-----------------------------------------------------------------------------------+
| SEPA Credit Transfer          | Disposizione paneuropea di accredito (bonifico)                                   |
|                               | eseguita secondo gli schemi e le regole definite da EPC.                          |
+-------------------------------+-----------------------------------------------------------------------------------+
| SPC                           | Sistema Pubblico di Connettività.                                                 |
+-------------------------------+-----------------------------------------------------------------------------------+
| SPCoop                        | Sistema Pubblico di Connettività e cooperazione.                                  |
+-------------------------------+-----------------------------------------------------------------------------------+
| Utilizzatore finale           | Cittadini, figure professionali o imprese, nonché                                 |
|                               | pubbliche amministrazioni che effettuano un pagamento                             |
|                               | elettronico a favore di un Ente Creditore.                                        |
+-------------------------------+-----------------------------------------------------------------------------------+


.. |pagoPA_logo| image:: media/header.png
   
