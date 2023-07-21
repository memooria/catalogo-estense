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
2. modificare i contenuti presenti nella folder [content](content)
3. creare una Pull Request sul master del repository principale
