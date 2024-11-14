SFEMovie C Adaptation for CSFML

Auteur : Yann GRALLAN

Description
Ce projet propose une adaptation de SFEMovie, initialement une extension de SFML permettant la lecture de vidéos, en C pour l'utiliser avec la bibliothèque CSFML.

L’objectif est de fournir une API en C permettant la lecture et l'intégration de vidéos dans des applications utilisant CSFML, offrant ainsi aux développeurs une manière simple d'incorporer des contenus multimédias dans leurs projets.

Fonctionnalités
Lecture de fichiers vidéo.
Gestion des formats vidéo et audio compatibles avec SFEMovie.
Synchronisation audio/vidéo.
Contrôle de lecture (pause, reprise, arrêt).
Intégration transparente avec CSFML.

```

#include <CSFML/Graphics.h>
#include "SFEMovie.h" // Nom du fichier d'en-tête de l'adaptation

int main() {
    // Initialisation de la fenêtre CSFML
    sfRenderWindow* window = sfRenderWindow_create(...);

    // Chargement d'une vidéo
    Movie* movie = Movie_create("path/to/video.mp4");

    // Boucle de rendu
    while (sfRenderWindow_isOpen(window)) {
        // Lecture et affichage de la vidéo
        Movie_play(movie);
        
        // Rendu de la vidéo sur la fenêtre
        sfRenderWindow_display(window);
    }

    // Libération des ressources
    Movie_destroy(movie);
    sfRenderWindow_destroy(window);

    return 0;
}

```

Licence
Ce projet est distribué sous la licence MIT. Consultez le fichier LICENSE pour plus de détails.

Remerciements
SFEMovie pour l'inspiration et la base technique.
CSFML pour sa puissante bibliothèque multimédia en C.
