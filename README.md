## Gallerie Estensi

## Come collaborare

1. creare un fork di questo repository
2. configurare Gihub Pages
  * Gihub repo > settings > Security >  Secrets and Variables > Actions > Variables
    aggiungere variable `PUBLIC_URL` con valore l'URL delle tue github pages
    Ad esempio: `mygithubuser.github.io`
  * Github repo > settigs > Code and Automation > Pages
    Scegliere un branch da cui rilasciare. Esempio: `master`. Come
    folder scegliere la cartella `/docs`
3. modificare i contenuti presenti nella folder [content](content)
4. inviare le modifiche al `master` del proprio repository
5. aspettare qualche minuto e valutare le modifiche sulla pagina `https://mygithubuser.github.io`
6. creare una PR dal proprio master al master del repo upstream

