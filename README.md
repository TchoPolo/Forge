# FORGE — Coach sportif

Application web autonome (aucune dépendance, aucun serveur) de coaching sportif complet : **callisthénie, musculation sur station à charge guidée, HIRT, course à pied et nutrition**.

## Fonctionnalités

- **7 objectifs** : physique & esthétique, force & skills, musculation (HG 90), performances course à pied, brûleur de graisse, complément HIRT, mobilité & santé — chacun avec son programme de 3 séances.
- **41 exercices illustrés** (SVG vectoriel généré) : technique pas à pas, erreurs fréquentes, chaîne de progression, lien vidéo.
- **Module musculation** calé sur les postes de la station Domyos HG 90 Boxe : développé assis, butterfly, tirage vertical, poulie basse, presse à jambes, sangle de cheville, sac de frappe.
- **Module HIRT** : circuits, EMOM, AMRAP, Tabata + créateur de circuits personnalisés, chrono guidé.
- **Journal de course à pied** intégré au générateur de séance et au suivi.
- **Coach vocal** (synthèse vocale hors-ligne) et **métronome de tempo 2-1-2**.
- **Générateur de séance du jour** basé sur l'historique des familles musculaires (fraîcheur 48 h, jours de course).
- **Difficulté ajustable** (Découverte / Normal / Intense) appliquée aux reps, durées et intervalles.
- **Suivi** : jardin de progression vivant, niveaux, badges, carnet de régularité, ressenti post-séance.
- **Cours** : 8 principes d'entraînement + 3 modules nutrition (déficit calorique, jours riches/modérés/pauvres, familles d'aliments).

## Structure

```
index.html                 l'application (HTML/CSS/JS en un seul fichier)
manifest.json              configuration PWA
sw.js                      service worker (fonctionnement hors-ligne)
icon-180/192/512(.maskable).png   icônes
```

Aucune étape de build : fichiers statiques servis tels quels.

## Déployer sur GitHub Pages

1. Pousse ces fichiers à la racine du dépôt (branche `main`).
2. **Settings → Pages** → *Deploy from a branch* → `main` → `/ (root)`.
3. L'app est en ligne sous 1 à 2 minutes à `https://<utilisateur>.github.io/<depot>/`.

## Installer sur téléphone

**iPhone (Safari)** : ouvre l'URL → icône de partage → *Sur l'écran d'accueil*.
**Android (Chrome)** : ouvre l'URL → bandeau *Installer l'application* (ou menu ⋮ → Installer).

L'app se lance en plein écran, sans barre de navigateur, et fonctionne hors-ligne.

## Données

Programme, historique, badges et séances personnalisées sont enregistrés **localement sur l'appareil** (`localStorage`). Rien n'est envoyé sur un serveur — et rien n'est synchronisé entre appareils.

## Mise à jour

Pousse les fichiers modifiés et incrémente la constante `CACHE` dans `sw.js`. Sur l'appareil : ouvrir l'app (téléchargement en arrière-plan), la fermer complètement, la rouvrir.
