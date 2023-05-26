REPOSITORY => {
    CREATE => {
        gh repo create                              | Permet de créer un repository
        Sans argument => création interactive   
        Options => {    
            --add-readme                            | Ajout d'un fichier README à la création
            -c, --clone                             | Clone le repository dans le dossier courant
            -d, --description "texte"               | Ajout de la description du repository
            --disable-issues                        | Désactive les issues sur le repository
            --disable-wiki                          | Désactive le wiki dans le repository
            -g, --gitignore "texte"                 | Spécifier un template de gitignore
            -h, --homepage "URL"                    | URL du repository distant
            --include-all-branches                  | Inclure un template de branches
            --internal                              | Faire un repository interne
            -l, --license "texte"                   | Spécifier une license Open Source
            --private                               | Rendre le repository privé
            --public                                | Rendre le repository publique
            --push                                  | Push les commits local sur le repository
            -r, --remote "nom du repository"        | Précise le nom du remote lié au repository
            -s, --source                            | Précise le chemin du repository local à utilisé comme source
            -t, --team "nom de l'organisation"      | Précise le nom de l'organisation qui a accès
            -p, --template "repository"             | Crée le repository sur la base d'un template de repository
        }
        Exemple => gh repo create --add-readme -c -d "Texte de description" -l MIT --public
    }
    LIST => {
        gh repo list                                | Permet de lister les repository
        Options => {
            --archived                              | Montre uniquement les repository archivés
            --fork                                  | Montre uniquement les repository forkés
            -q, --jq "expression"                   | Filtre avec une sortie JSON utilisant l'expression jq
            --json "champs"                         | Sortie JSON avec les champs spécifié
            -l, --language "nom du language"        | Filtre en fonction du language principale
            -L, --limit                             | Nombre maximum de repository listés
            --no-archived                           | Omettre les repository archivés
            --source                                | Affiche seulement les repository non forké
            -t, --template "texte"                  | Sortie en JSON utilisant un template Go (voir gh help formating)
            --topic "texte"                         | Filtrer par topic
            --visibility "texte"                    | Filtrer par visibilité du repository (public, private, internal)
        }
        Exemple => gh repo list -l javascript --no-archived
    }
    ARCHIVE => {
        gh repo archive "repository"                | Permet d'archiver un repository (Si pas d'argement, repository courant)
        Option => {
            -y, -yes                                | Skip la confirmation prompt
        }
        Exemple =>  gh repo archive git@github.com:Pverdiere/formation-dotnet-cheatsheets.git -y
    }
    CLONE => {
        gh repo clone "repository"                  | Permet de cloner un repository
        Option => {
            -u, --upstream-remote-name "texte"      | Nom du remote upstream lors d'un clonage fork
        }
        Exemple => gh repo clone git@github.com:Pverdiere/formation-dotnet-cheatsheets.git
    }
    DELETE => {
        gh repo delete "repository"                 | Permet de supprimer un repository GitHub (Si pas d'argument, repository courant)
        Option => {
            --yes                                   | confirmation sans la validation prompt
        }
        Exemple => gh repo delete git@github.com:Pverdiere/formation-dotnet-cheatsheets.git --yes
    }
    DEPLOY-KEY => {
        gh repo deploy-key                          | Permet la gestion des clés dans le repository
        add => {
            gh repo deploy-key add <key-file>       | Ajout une clé ssh au repository GitHub
            Options => {
                -w, --allow-write                   | Ajout les droits d'écriture pour la clé
                -t, --title "texte"                 | Titre de la clé
            }
            Exemple => gh repo deploy-key add ~/.ssh/gh-test.pub
        }
        delete => {
            gh repo deploy-key delete <key-id>      | Suppression d'une clé du repository GitHub
        }
        list => {
            gh repo deploy-key list                 | Liste les clés du repository GitHub
        }
        Options => {
            -R, --repo <[HOST/]OWNER/REPO>          | Permet de selectionner un autre repository en utilisant le format [HOST/]OWNER/REPO
        }
    }
    EDIT => {
        gh repo edit "repository"                   | Permet de modifier les options d'un repository
        Options => {
            --add-topic "texte"                     | Ajout d'un sujet au repository
            --allow-forking                         | Autorise le fork du repository
            --allow-update-branch                   | Autorise les pull request sur la branch HEAD
            --default-branch "nom de la branch"     | Set la branch par défault du repository
            --delete-branch-on-merge                | supprime la branch HEAD lorsque le pull request est merge
            -d, --description "texte"               | Ajout d'une description au repository
            --enable-auto-merge                     | Active l'auto merge
            --enable-discussions                    | Active les discussions sur le repository
            --enable-issues                         | Active les issues sur le repository
            --enable-merge-commit                   | Active le merge de pull request via un merge commit
            --enable-project                        | Active les projets dans le repository
            --enable-rebase-merge                   | Active le merge de pull request via le rebase
            --enable-squash-merge                   | Active le merge de pull request via squashed commit
            --enable-wiki                           | Active le wiki pour le repository
            -h, --homepage URL                      | Ajout de la page d'acceuil du repository
            --remove-topic "texte"                  | Suppression d'un sujet du repository
            --template                              | Rendre le repository valide comme template
            --visibility "texte"                    | Change la visibilité du repository (public,private,internal)
        }
        Exemple => gh repo edit --enable-issues --enable-wiki
    }
    FORK => {
        gh repo fork "repository"                   | Crée un fork d'un repository
        Options => {
            --clone                                 | Clone le repository forké
            --default-branch-only                   | Inclut uniquement la branche par défault dans le fork
            --fork-name "texte"                     | Renome le repository forké
            --remote                                | Ajout d'un remote pour le fork
            --remote-name "texte"                   | Spécifie le nom pour le nouveau remote
        }
        Exemple => gh repo fork https://github.com/Simplon-hdf/formation-dotnet-cheatsheets.git --clone --remote --remote-name cheatSheetSimplon
    }
    RENAME => {
        gh repo rename "texte"                      | Renome le repository
        Options => {
            -R, --repo <[HOST/]OWNER/REPO>          | Selectionne un autre repository en utilisant le format [HOST/]OWNER/REPO
            -y, --yes                               | Skip la confirmation prompt
        }
        Exemple => gh repo rename newName
    }
    SET-DEFAULT => {
        gh repo set-default "repository"            | Définit le repository distant par défaut lors de l'interrogation de l'API GitHub pour le repository local
        Options => {
            -u, --unset                             | Déselectionne le repository par défaut actuel
            -v, --view                              | Montre le repository par défaut actuel
        }
        Exemple => gh repo set-default -v
    }
    SYNC => {
        gh repo sync <destination-repository>       | Permet de resynchronisé avec le repository source
        Options => {
            -b, --branch "texte"                    | Synchonise une branch spécifique
            --force                                 | Hard reset de la branch du destination-repository pour correspondre à la source repository
            -s --source "texte"                     | Choisi une source différente de de la source par défaut
        }
        Exemple => gh repo sync --branch v1
    }
    UNARCHIVE => {
        gh repo unarchive "repository"              | Désarchive un repository GitHub
        Option => {
            -y, --yes                               | Skip la confirmation du prompt
        }
        Exemple => gh repo unarchive git@github.com:Pverdiere/formation-dotnet-cheatsheets.git -y
    }
    VIEW => {
        gh repo view "repository"                   | Affiche la description et le README du repository GitHub
        Options => {
            -b, --branch "texte"                    | affiche une branch spécifique du repository
            -q, --jq <expression>                   | Filtre JSON en sortie, utilisant une expression jq
            --json "champs"                         | Sortie JSON avec les champs spécifiés
            -t, --template "texte"                  | Sortie en JSON utilisant un template Go (voir gh help formating)
            -w, --web                               | Ouvre le repository dans le navigateur
        }
        Exemple => gh repo view git@github.com:Pverdiere/formation-dotnet-cheatsheets.git -w
    }
}