Questo repository contiene il codice e i file di simulazione per il progetto dell'esame di Identificazione, tenuto dal prof. A. Cavallo, anno accademico 2025/26

Il progetto affronta la modellazione, l'identificazione e il controllo di una flotta di veicoli, con l'obiettivo di mantenere le distanze di sicurezza e le velocità desiderate tramite controllori MPC (Model Predictive Control)

Panoramica del Progetto
Il flusso di lavoro del progetto è diviso in tre fasi principali:
Inizializzazione e Setup Fisico: Vengono definiti i parametri fondamentali del problema, come il tempo di headway (t_cth = 3 s), la distanza minima di sicurezza (dmin = 4 m), i limiti della forza di trazione (umax = 600 N e umin = -600 N) e il tempo di campionamento (Ts = 2 s)
. Vengono inoltre stabilite le condizioni iniziali di velocità (v0) e distanza inter-veicolare (d0) per una flotta di 5 veicoli

Identificazione dei Sistemi: A partire dai dati raccolti, vengono stimate le funzioni di trasferimento (es. modelli ARX) per le velocità e le distanze inter-veicolari di ciascun veicolo
. Questi modelli vengono poi combinati per generare 4 sistemi SIMO (Single Input Multiple Output) in spazio di stato, in cui l'ingresso è l'azione di controllo u(i) e le uscite sono la velocità dell'auto vel(i) e la distanza rispetto al veicolo che la precede

Controllo in Simulink: L'ambiente Simulink è utilizzato per la validazione. Inizialmente, il modello di ogni singola auto viene stabilizzato intorno al proprio punto di equilibrio
. Successivamente, i controllori MPC (basati sui 4 sistemi SIMO identificati precedentemente) vengono implementati per gestire la dinamica della flotta
. Infine, vengono analizzati e confrontati i grafici per valutare le prestazioni del controllo
