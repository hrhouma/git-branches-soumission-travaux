# git-branches-soumission-travaux

# Guide d'Installation et de Configuration de Projet

## Prérequis
Avant de commencer, assurez-vous d'avoir installé sur votre machine:
- .NET SDK
- Visual Studio Code
- Git

## Étapes d'Installation

### 1. Aller à bureau
Ouvrez un explorateur de fichiers et naviguez vers votre bureau.

### 2. Ouvrir la ligne de commande (cmd)
- Pressez `Win + R`, tapez `cmd`, et pressez `Entrée`.
- cd Desktop (ou cd Bureau)


### 3. Créer un dossier pour le projet
Tapez la commande suivante dans le terminal cmd:
```bash
mkdir chapitre1_votre_nom
```

### 4. Naviguer dans le dossier créé
Exécutez:
```bash
cd chapitre1_votre_nom
```

### 5. Créer un nouveau projet console .NET
```bash
dotnet new console -o code1
```

### 6. Entrer dans le dossier du projet
```bash
cd code1
```

### 7. Ouvrir le projet dans Visual Studio Code
```bash
code .
```

### 8. Fermer tous les autres terminaux
Assurez-vous que tous les terminaux autres que celui de VS Code soient fermés.

### 9. Examiner le fichier `Program.cs`
Naviguez vers le fichier `Program.cs` dans VS Code et ouvrez-le.

### 10. Ouvrir le terminal intégré de VS Code
Naviguez vers `...` > `Terminal` > `New Terminal`.

### 11. Exécuter le projet
Dans le terminal de VS Code, tapez:
```bash
dotnet run
```

### 12. Copiez et collez le code initial dans `Program.cs`
Remplacez le contenu de `Program.cs` par le code suivant, puis sauvegardez et exécutez:
```csharp
using System;
namespace Recherche1
{
    class Program
    {
        // Méthode principale de l’application.
        static void Main(string[] args)
        {
            // Déclaration des variables nécessaires pour l’application.
            int Cnt = 0;
            bool Trouve = false;
            string Test = "";
            // Déclaration et initialisation des tableaux.
            string[] Noms = new string[] { "Marc", "Martine", "François", "Charlotte",
 "Daniel", "Patricia", "Gregory", "Yves", "Louise",
 "Carl" };
            int[] Moyennes = new int[] { 95, 78, 65, 88, 90, 85, 66, 86, 90, 75 };
            // Récupération de la saisi du nom de l’étudiant que l’utilisateur désire trouvé.
            Console.Write(" Donnez-moi le nom de l’étudiant recherché : ");
            Test = Console.ReadLine().ToLower();
            Console.ReadKey();
        }
    }
}
```

### 13. Exécuter le projet pour valider
Dans le terminal, tapez:
```bash
dotnet run
```

## Configuration de Git

### 14. Initialisation de Git
Dans le terminal de VS Code, tapez:
```bash
git init
```

### 15. Installer l'extension gitignore
Utilisez l'onglet extensions de VS Code pour installer un gestionnaire de `.gitignore`.

### 16. Ajouter un fichier `.gitignore`
Créez un fichier `.gitignore` et ajoutez:
```
bin/
obj/
*.csproj
*.sln
```

### 17. Ajouter les fichiers au dépôt
```bash
git add .
git status
```

### 18. Configurer les informations utilisateur pour Git
```bash
git config --global user.name "hrhouma"
git config --global user.email "rehoumahaythem@gmail.com"
git config --local user.name "VotreNom"
git config --local user.email "VotreEmail@gmail.com"
```

### 19. Commit initial
```bash
git commit -m "ajout du premier code"
git status
```

## Création d'un dépôt sur GitHub

### 20. Créer un dépôt nommé `examen_resolution` sur GitHub
Assurez-vous de ne pas initialiser avec un fichier README.md.

### 21. Lier le dépôt local au dépôt distant et pousser
```bash
git remote add

 origin https://github.com/hrhouma/examen_resolution.git
git branch -M exercice1
git push -u origin exercice1
```

## Modification et Gestion de Branches

### 22. Créer une nouvelle branche pour les modifications
```bash
git checkout -b exercice2
```

### 23. Appliquer les modifications
Copiez le deuxième exemple de code dans `Program.cs`, sauvegardez, puis:
```csharp
using System;
namespace Recherche1
{
    class Program
    {
        // Méthode principale de l’application, qui est le point d'entrée du programme.
        static void Main(string[] args)
        {
            // Déclaration d'un compteur utilisé pour parcourir les tableaux.
            int Cnt = 0;
            // Variable booléenne pour indiquer si le nom recherché a été trouvé.
            bool Trouve = false;
            // Variable pour stocker le nom de l'étudiant entré par l'utilisateur.
            string Test = "";

            // Déclaration et initialisation du tableau des noms d'étudiants.
            string[] Noms = new string[] { "Marc", "Martine", "François", "Charlotte",
                                           "Daniel", "Patricia", "Gregory", "Yves", "Louise",
                                           "Carl" };
            // Déclaration et initialisation du tableau des moyennes associées aux étudiants.
            int[] Moyennes = new int[] { 95, 78, 65, 88, 90, 85, 66, 86, 90, 75 };

            // Demande à l'utilisateur de saisir le nom de l'étudiant recherché.
            Console.Write("Donnez-moi le nom de l'étudiant recherché: ");
            // Lecture de la saisie utilisateur, conversion en minuscules pour faciliter la comparaison.
            Test = Console.ReadLine().ToLower();

            // Boucle pour parcourir le tableau des noms.
            while (Cnt < Noms.Length && !Trouve)
            {
                // Comparaison du nom saisi avec les noms dans le tableau.
                if (Test == Noms[Cnt].ToLower())
                {
                    // Si trouvé, mettre Trouve à true pour arrêter la boucle.
                    Trouve = true;
                    // Affichage de la moyenne de l'étudiant trouvé.
                    Console.WriteLine("La moyenne de {0} est {1}.", Noms[Cnt], Moyennes[Cnt]);
                }
                // Incrémentation du compteur pour passer à l'élément suivant du tableau.
                Cnt++;
            }

            // Si après la recherche, Trouve est toujours false, indiquer que l'étudiant n'est pas trouvé.
            if (!Trouve)
            {
                Console.WriteLine("Étudiant non trouvé.");
            }

            // Attente que l'utilisateur appuie sur une touche avant de fermer la console.
            Console.ReadKey();
        }
    }
}
```

### 24. Vérifier les branches sur GitHub
Naviguez sur GitHub pour voir les branches `exercice1` et `exercice2`.

## Conclusion

Félicitations ! Vous avez maintenant configuré et géré deux versions d'un projet dans des branches différentes avec Git et GitHub.


