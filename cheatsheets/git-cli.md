REPOSITORY => {
    CREATE => {
        gh repo create
        Sans argument => création interactive
        Options => {
            --add-readme                        | Ajout d'un fichier README à la création
            -c, --clone                         | Clone le repository dans le dossier courant
            -d, --description "texte"           | Ajout de la description du repository
            --disable-issues                    | Désactive les issues sur le repository
            --disable-wiki                      | Désactive le wiki dans le repository
            -g, --gitignore "texte"             | Spécifier un template de gitignore
            -h, --homepage "URL"                | URL du repository distant
            --include-all-branches              | Inclure un template de branches
            --internal                          | Faire un repository interne
            -l, --license "texte"               | Spécifier une license Open Source
            --private                           | Rendre le repository privé
            --public                            | Rendre le repository publique
            --push                              | Push les commits local sur le repository
            -r, --remote "nom du repository"    | Précise le nom du remote lié au repository
            -s, --source                        | Précise le chemin du repository local à utilisé comme source
            -t, --team "nom de l'organisation"  | Précise le nom de l'organisation qui a accès
            -p, --template "repository"         | Crée le repository sur la base d'un template de repository
        }
        Exemple => gh repo create --add-readme -c -d "Texte de description" -l MIT --public
    }
}