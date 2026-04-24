# PLC Washing Machine Control (Codesys)
Progetto d'esame per il corso di **Ingegneria e Tecnologie dei Sistemi di Controllo** presso l'Università di Bologna. Il sistema realizza il controllo logico completo di una lavatrice industriale, gestendo cicli di lavaggio, attuatori e diagnostica di sicurezza.

## Architettura e Logica di Controllo
Il software è stato sviluppato in ambiente **Codesys V3.5 SP19** adottando una soluzione basata sugli **Attuatori Generalizzati (GA)** e uno schema di policy "padre-figlio" per la gestione dei componenti.

* **SFC (Sequential Function Chart):** Utilizzato per la modellazione della logica sequenziale delle fasi di lavaggio (Pre-lavaggio, Lavaggio, Risciacquo, Scarico).
* **ST (Structured Text):** Utilizzato per la logica di controllo degli attuatori e la gestione dei fault.

## Gestione dei Fault
Il sistema è progettato per rilevare e gestire guasti critici secondo diverse priorità:
1.  **Fault Riscaldamento:** Rilevamento avaria resistenza; segnalazione allarme e proseguimento del ciclo a freddo.
2.  **Fault Immissione Acqua:** Interruzione immediata del ciclo e scarico di sicurezza in caso di ostruzione.
3.  **Fault Scarico:** Arresto di sicurezza della fase corrente in caso di mancato svuotamento del cestello.

## Interfaccia HMI
Il progetto include la logica per un'interfaccia operatore che permette di:
* Selezionare il programma e la temperatura di lavaggio.
* Monitorare in tempo reale lo stato degli attuatori (motore, pompa, valvole).
* Visualizzare gli allarmi specifici per la manutenzione.
