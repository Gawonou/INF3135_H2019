# S�ance 3: Cha�nes de caract�res, pointeurs et matrices

**Note**: Il est recommand� de versionner vos r�ponses aux exercices � l'aide
de Git (un seul d�p�t est amplement suffisant pour la s�ance, ou m�me un seul
d�p�t pour tous les laboratoires, en divisant les fichiers dans des
r�pertoires).

## 1 - Cha�nes de caract�res

�crivez un petit programme C appel� `renverse.c` qui prend tous les arguments
pass�s en param�tres, les concat�ne en ordre inverse et affiche le r�sultat.

On s'attend donc au comportement suivant :

```sh
./renverse alpha beta gamma delta
deltagammabetaalpha

./renverse esope reste et se repose
reposeseetresteesope
```

N'h�sitez pas � utiliser la biblioth�que `string.h`.

## 2 - Palindromes

�crivez une fonction C dont la signature est
```c
bool estPalindrome(const char *s);
```
qui retourne `true` si et seulement si `s` est un palindrome, c'est-�-dire un
mot qui se lit de la m�me fa�on de gauche � droite. On s'attend donc � ce que
```c
estPalindrome("radar")
estPalindrome("ici")
estPalindrome("laval")
estPalindrome("!RessasseR!")
estPalindrome("")
estPalindrome("U")
```
retournent `true`, mais que
```c
estPalindrome("Lui")
estPalindrome("Ici")
estPalindrome("laval.")
estPalindrome("Esope reste et se repose.")
```
retournent `false`.

Ensuite, �crivez une fonction C dont la signature est
```c
bool estPhrasePalindrome(const char *s);
```
qui v�rifie si une phrase est palindromique, en ignorant la casse
(majuscules/minuscules) et les signes de ponctuation. Ainsi, on s'attend � ce
que
```c
estPhrasePalindrome("Esope reste et se repose.")
estPalindrome("Ici")
```
retournent `true`.

Dans les deux cas, fournissez des tests pour montrer que vos fonctions sont
correctement impl�ment�es.

## 3 - Fouille dans un tableau

�crivez une fonction C dont la signature est
```c
const double *trouverElement(const double tableau[],
                       unsigned int taille,
                       double element);
```
qui retourne un pointeur vers la premi�re occurrence de `element` dans
`tableau` si elle existe, ou qui retourne `NULL` sinon, sachant que les indices
valides de `tableau` sont entre `0` et `taille - 1`.

## 4 - Afficher une matrice

�crivez une fonction C permettant d'afficher le contenu d'une matrice d'entiers
de dimensions 3 par 3.

Rappelons qu'on peut initialiser une matrice de la fa�on suivante
```c
int matrice[3][3] = { {1, 2, 3}, {4, 5, 6}, {7, 8, 9} };
```
Bien s�r, vous trouverez un moyen d'�liminer les valeurs magiques sp�cifiant la
taille de la matrice. L'en-t�te de votre fonction devrait ressembler �
```c
void afficherMatrice(int matrice[3][3]);
```

Gr�ce � votre fonction, la matrice sera affich�e comme suit:
```
1 2 3
4 5 6
7 8 9
```

## 5 - Addition de matrices

�crivez une fonction C permettant d'additionner deux matrices.  N'h�sitez pas �
r�utiliser la fonction de l'exercice pr�c�dent pour afficher le r�sultat.
L'en-t�te de votre fonction devrait ressembler �
```c
void additionnerMatrices(int matrice1[3][3],
                         int matrice2[3][3],
                         int resultat[3][3]);
```

Voici un exemple de sortie attendue:

```
1 2 3
3 2 1
1 2 3
+
4 3 2
2 3 4
4 3 2
=
5 5 5
5 5 5
5 5 5
```
---

Auteur original Alexandre Blondin Mass�