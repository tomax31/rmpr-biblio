# Bibliographie RMPR / RNS

**Bibliographie dynamique des Rencontres Méridionales de Préhistoire Récente (RMPR) et des Rencontres Nord/Sud de Préhistoire Récente (RNS)**

🌐 **[Consulter la bibliographie en ligne](https://tomax31.github.io/rmpr-biblio/)**

## Présentation

Cet outil permet de consulter, rechercher, filtrer et exporter les références bibliographiques des publications issues des **Rencontres Méridionales de Préhistoire Récente (RMPR)** et des **Rencontres Nord/Sud de Préhistoire Récente (RNS)**.

Les données proviennent de la bibliothèque collaborative [BDA Biblio](https://www.zotero.org/groups/154609/bda_biblio), hébergée sur Zotero.

La bibliographie est générée dynamiquement à partir des notices portant les marqueurs (*tags*) `RMPR` ou `RNS`. Elle est actualisée à chaque chargement de la page, sans nécessiter d'exportation ou de mise à jour manuelle.

L'outil est accessible depuis le [site des RMPR](https://blogs.univ-tlse2.fr/rmpr/publications/).

## Fonctionnalités

### Consultation et recherche

- Récupération automatique des références depuis l'API Zotero.
- Gestion de la pagination permettant de consulter plusieurs centaines de références.
- Suppression des doublons entre les deux corpus.
- Classement chronologique décroissant par année de publication.
- Regroupement des références par année, avec possibilité de replier ou déplier les sections.
- Recherche textuelle par auteur, titre, année, mots-clés et autres informations bibliographiques.
- Filtrage par corpus : RMPR, RNS ou ensemble des deux.
- Affichage du nombre total de références distinctes et des effectifs propres à chaque corpus.

### Styles bibliographiques

Les références peuvent être affichées selon quatre styles bibliographiques CSL (*Citation Style Language*) :

- **ISO 690** (auteur-date)
- **APA**
- **Bulletin de la Société préhistorique française (BSPF)**
- **Gallia Préhistoire**

La mise en forme est produite par Zotero, à partir des styles CSL correspondants.

### Exportation

La bibliographie affichée peut être exportée sous deux formes :

- **PDF** : par l'intermédiaire de la fonction d'impression du navigateur.
- **LibreOffice Writer** : exportation au format HTML, compatible avec LibreOffice Writer et pouvant ensuite être enregistrée au format ODT.

Les exports tiennent compte des filtres et des recherches appliqués, ainsi que du style bibliographique sélectionné.

## Fonctionnement technique

L'application est développée en **HTML, CSS et JavaScript natif**, sans framework ni serveur applicatif.

Elle repose sur :

- **GitHub Pages**, pour l'hébergement de l'interface ;
- **l'API publique Zotero**, pour l'accès aux données bibliographiques ;
- **les styles CSL de Zotero**, pour la mise en forme des références.

Le programme interroge le groupe Zotero n° `154609`, en sélectionnant les notices portant les marqueurs `RMPR` et `RNS`.

Les données sont récupérées au format JSON, par lots de 100 références, afin de contourner les limitations de volume des exports bibliographiques directs de l'API.

Les résultats sont fusionnés en utilisant les identifiants uniques des notices Zotero, ce qui évite de compter deux fois une référence portant les deux marqueurs.

Lors d'un changement de style bibliographique, une nouvelle interrogation de l'API permet de récupérer les références dans le format demandé.

Aucune donnée bibliographique n'est stockée de manière permanente par l'application.

## Installation et déploiement

L'application est contenue dans un fichier unique :

`index.html`

Elle peut être hébergée sur n'importe quel serveur Web statique.

Pour un déploiement sur GitHub Pages :

1. Créer un dépôt GitHub public.
2. Ajouter le fichier `index.html` à la racine du dépôt.
3. Activer GitHub Pages dans **Settings → Pages**.
4. Sélectionner la branche `main` et le dossier `/ (root)`.

L'application est alors accessible à l'adresse GitHub Pages du dépôt.

## Maintenance et mise à jour

### Mise à jour des références

Aucune intervention dans le code n'est nécessaire pour actualiser la bibliographie.

Il suffit d'ajouter ou de modifier les références dans la bibliothèque Zotero **BDA Biblio**, puis de leur attribuer le marqueur `RMPR` ou `RNS`.

Les modifications deviennent visibles lors d'un nouveau chargement de la page, après synchronisation des données Zotero.

### Modification des styles bibliographiques

Les styles proposés sont définis dans le menu HTML :

```html
<select id="style">
```

Chaque option correspond à l'identifiant d'un style CSL reconnu par Zotero.

### Utilisation avec une autre bibliothèque Zotero

Le programme peut être adapté à un autre groupe Zotero en modifiant les constantes JavaScript :

```javascript
const GROUP = 154609;
const TAGS = ["RMPR", "RNS"];
```

Le groupe doit être accessible publiquement pour permettre la consultation sans authentification.

## Limites

- Une connexion Internet est nécessaire pour accéder aux données Zotero.
- Le temps de chargement dépend du nombre de références et du temps de réponse de l'API.
- Le changement de style bibliographique peut nécessiter plusieurs requêtes supplémentaires.
- La qualité des références affichées dépend de la qualité des métadonnées saisies dans Zotero.
- L'export Writer est un document HTML compatible, et non un fichier ODT natif.

## Liens utiles

- [Site des RMPR](https://blogs.univ-tlse2.fr/rmpr/)
- [Bibliographie RMPR / RNS](https://tomax31.github.io/rmpr-biblio/)
- [Groupe Zotero BDA Biblio](https://www.zotero.org/groups/154609/bda_biblio)
- [Documentation de l'API Zotero](https://www.zotero.org/support/dev/web_api/v3/start)
- [Répertoire des styles CSL](https://www.zotero.org/styles)

## Auteur et crédits

**Thomas Perrin — 2026**

Outil développé pour faciliter l'accès aux publications des Rencontres Méridionales de Préhistoire Récente et des Rencontres Nord/Sud de Préhistoire Récente.

Développement réalisé avec l'assistance de ChatGPT (OpenAI).

Les références bibliographiques restent la propriété intellectuelle de leurs auteurs et éditeurs respectifs.

---

*Dernière mise à jour de la documentation : octobre 2026.*
