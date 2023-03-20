https://git-scm.com/

Git è un software open source e gratis, aiuta i sviluppatori
versionare il codice tiene traccia tutta la storia su quello che stiamo lavorando

piu' rami = branch
branch principale 
main master = ramo principali
branch secondari= andiamo a creare le nostre modifiche e lo testiamo il nostro progetto
con esito positivo allora facciamo il merge (unire versione vecchia con nuovi rami)

- possiamo tenere traccia di tutte le modifiche effettuate tramite commit
- lavorare in team in maniera semplificata, condivisione del codice
 
 1) Fase
 - inizializzare una repository in un punto locale
 - comando  su terminale per inizializzare : git init
 - creare un file index.html e popolarlo
 - comando dello stato: git status
 -- ci dice che siamo su branch master (ramo principale)
 -- nessun commit ancora
 -- ci dice che non sono file tracciati (modifiche per renderlo tracciato)
    comando git add index.html
    comando git status e ci dice che ci sono cambiamenti per fare il commit,
    nella schermata EXPORER il file index.html la U è diventato una A (sta per ADD)
 --spiegazione schema processo git:
    -aggiunge un file alla nostra working directory
    - con il comando add abbiamo aggiunto alla staging area
    - una volta che tutte le modifiche sono nella staging area possiamo fare un commit
    - salviamo in una cartella locale chiamata .git
    - possiamo salvare in repository remote[github] le nostre modifiche con il comando push
-- comando per commit
    -git commit -m "added index.html"
    - commitato regolarmente 1 file cambiato 18 righe
    - git status
-- aggiungere altri file tracciati
    - creare due file about.html e style.css
    - git add . (tutti i file nel nostro working directory )
    - git -m "added style.css and about page"
-- creare una repository online (github)
    - click tasto verde New a alto sx
    - scriviamo il nome della repository corso-git
    - Repo online del Corso Git YT
    - publico o privato
    - Aggiungere file README
    - aggiunge file .gitignore (aggiungere dei file che git non lo prenda in considerazione)
    - click Creating repository
    - due opzioni 
    - noi scegliamo la seconda "or push an existing repository from the command line"
    - copia e incolla
    - su github abbiamo 3 file su branch main
    - nome account vicino all'ultimo messaggio del commit
    - a fianco ad ogni file abbiamo il messaggio ultimo del commit
    - aggiungere testo html nel file about.html e fare git add . e git commit -m "added about page structure"
    - comando per metterlo nel branch main di github: git push origin main

-- Discorso sul branch main
    - backup dello stato attuale del branch main
    - git status
    - git branch test
    - spostarci sulla nuova branch: git checkout test
    - git push origin test (passare nel branch secondario su github)
    - git switch main (tornare sul branch main o master)
    - git checkout -b test (creare un branch e farci il checkout)
    - git push origin test1 (creare un branch secondario su github)
    - riempire il file style.css
    - git status
    - git push --set-upstream origin test1
    - creare nuovo file prova.html
    - git add .
    - git commit -m ""
    - git push (perché gia impostato)
    - comando git checkout main (testare branch main)
    - comando git checkout - (branch precedente)

    Aggiungere testo nel file prova.html
    - git checkout main
     --Abort (Esegui il commit o lo stash delle modifiche prima di cambiare)
     -- in poche parole se siamo in working directory o in Staging area non possiamo uscire dal 
     branch senza aver fatto un commit alle modifiche
    - nel momento che siamo nella fase local .git dopo il commit possiamo cambiare il branch

    Aggiungere modifica index.html e file about.css
    - git status
    - git restore index.html (annulla le modifiche e ritorna indietro)
    - git status
    - git add .
    - git status
    - git restore --staged index.html (togliere il file index.html dallo stage)
    - git status (index.html ritorna nella cartella working directory)
    - git restore index.html (cancella la modifica)
    - git checkout - (passiamo al main branch)
    Visualizzare una lista di branch:
    - git branch
    Cancellare branch da remoto
    -  click su branch 
    - nella sezione Your branches 
    - click cestino a dx
    Cancellare branch in remoto da locale
    - git checkout test
    - git push origin --delete test
    Cancellare branch test in locale
    - git branch
    - git checkout main
    - git branch -D test
    - git branch
    Merge di due branch (Unire)
    - git checkout main (main che ricevere i cambiamenti)
    - git merge test1
    - git push origin main (aggiornare nel git remoto)
    Mettere da parte le modifiche fatte
    - git checkout -
    - modifichiamo il file prova.html
    - git stash (salve le modifiche in un array)
    - git stash list (lista dei salvataggi)
    - git checkout -
    - git checkout -
    - git stash pop (recuperiamo le modifiche)
    - git status
    Simuliamo un lavoro hotfix
    - git stash
    - git checkout - (main)
    - modifichiamo index.html
    - git add index.html
    - git commit -m "hotfix"
    - git push
    - git checkout test1
    - git stash pop
    - git status
    - git stash
    - modifichiamo file index.html
    - git stash
    - git stash list
    - git stash clear (pulire lista)
    - git stash list
    Creare una branch su github
    - sito web github
    - click create a branch
    - branch source main
    - creare README
    - ritorniamo al terminale
    - git branch (non c'è)
    - git checkout prova (error)
    - git fetch
    - git checkout prova
    - git add .
    - git commit -m "prova"
    - git push