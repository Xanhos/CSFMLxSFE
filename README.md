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
#include "SFML/Graphics.h"

int main()
{
	sfRenderWindow* window = sfRenderWindow_create(sfVideoMode_getDesktopMode(), "SFML", sfDefaultStyle, NULL);

	sfeMovie* movie = sfeMovie_createFromFile("YOUR//FILE");
	sfeMovie_play(movie);
	sfeMovie_fit(movie, (sfFloatRect) {0,0, 1920 , 1080}, sfTrue);
	sfeMovie_setVolume(movie, 50.f);
	sfEvent event;
	while (sfRenderWindow_isOpen(window))
	{
		while (sfRenderWindow_pollEvent(window, &event))
		{
			if (event.type == sfEvtClosed)
			{
				sfRenderWindow_close(window);
			}
		}
		sfeMovie_update(movie);

		sfRenderWindow_clear(window, sfBlack);
		sfRenderWindow_drawMovie(window, movie, NULL);
		sfRenderWindow_display(window);

	}

return 0;
}

```

Licence
Ce projet est distribué sous la licence MIT. Consultez le fichier LICENSE pour plus de détails.

Remerciements
SFEMovie pour l'inspiration et la base technique.
CSFML pour sa puissante bibliothèque multimédia en C.
