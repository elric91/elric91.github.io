Il existe plusieurs techiques sous [linux|tag:linux] pour splitter un fichier [audio|tag:audio] (i.e. flac) à partir de son fichier cue.
La plus universelle que j'aie trouvée (qui s'accomode par exemple de caractères bizarres dans les cuesheets) est de créer un fichier shell du type suivant :
 
> # splitit.sh
> cuebreakpoints *.cue | shnsplit -o flac *.$1 && cuetag *.cue split*.flac

et pour l'utiliser (en partant du principe que le fichier ".wv" à splitter et la cuesheet sont dans le même répertoire) :

> ~/splitit.sh wv
