# Rick & Morty Multiplatform App

Bienvenue dans ce projet basé sur l’univers de Rick & Morty ! Il s’agit d’une application développée en **Kotlin Multiplatform** qui vise à fonctionner sur **Android, iOS, Web et Desktop**, en partageant un maximum de code grâce à **Jetpack Compose Multiplatform**.

---

## Architecture du projet Android

L’architecture repose sur **Kotlin Multiplatform**, ce qui signifie qu’on écrit une grande partie du code une seule fois, et il est réutilisé sur toutes les plateformes. Voici comment tout ça s’organise :

### `composeApp/`
C’est le cœur du projet. Il contient tout le code commun utilisé par toutes les plateformes : logique métier, appels API, et interface utilisateur via **Compose Multiplatform**.

À l’intérieur, on retrouve plusieurs "sources sets" :

- `commonMain` → le code partagé (UI, logique, data, etc.).
- `androidMain`, `iosMain`, etc. → des dossiers pour écrire du code spécifique à une plateforme quand c’est nécessaire.

### `androidApp/`
C’est la partie Android native du projet. Elle contient :
- Le point d’entrée de l’app Android (`MainActivity.kt`)
- La configuration Gradle pour Android
- Et éventuellement des éléments propres à Android comme les permissions ou les fichiers de ressources (images, strings, etc.)

### Côté technique
- L’interface est faite avec **Jetpack Compose**, mais comme on utilise Compose Multiplatform pour que le même code d’UI tourne sur iOS, Web, et Desktop.
- La communication avec l’API Rick & Morty se fait via **Ktor**.
- L’architecture suit une approche assez classique MVI, facilitée par les ViewModels de KMP.

---

## Lancer le projet Android
1. Clone le repo
2. Ouvre-le dans Android Studio
3. Lance `androidApp` comme une app Android classique

---

