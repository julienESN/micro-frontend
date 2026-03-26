# PixelArena - Sprint Final CP7

Repository de rendu pour le sprint final Micro-Frontends.

Le checkpoint cible dans ce repo est `pixelarena-checkpoint7/`.
La branche de rendu contenant le correctif demandé est `partie-7`.

## Objectif

Valider le CP7 "L'Assemblage Final" :

- le `Header` ecoute l'evenement `game:joined` emis par le `Lobby`
- le `Header` ecoute l'evenement `cart:updated` emis par le `Cart`
- les badges du `Header` se mettent a jour en consequence

## Architecture

L'application est composee de 5 micro-frontends :

- `shell` : application hote, port `3000`
- `mfe-header` : header global, port `3001`
- `mfe-lobby` : liste des parties, port `3002`
- `mfe-catalog` : boutique, port `3003`
- `mfe-cart` : panier, port `3004`

Communication inter-MFE via un event bus partage.

## Prerequis

- `Node.js`
- `npm`
- 5 terminaux ouverts en parallele

## Lancement

Depuis la racine du repo :

```bash
cd pixelarena-checkpoint7/mfe-header
npm install
npm start
```

Dans un deuxieme terminal :

```bash
cd pixelarena-checkpoint7/mfe-lobby
npm install
npm start
```

Dans un troisieme terminal :

```bash
cd pixelarena-checkpoint7/mfe-catalog
npm install
npm start
```

Dans un quatrieme terminal :

```bash
cd pixelarena-checkpoint7/mfe-cart
npm install
npm start
```

Dans un cinquieme terminal :

```bash
cd pixelarena-checkpoint7/shell
npm install
npm start
```

## URLs utiles

- Shell : [http://localhost:3000](http://localhost:3000)
- Header : [http://localhost:3001](http://localhost:3001)
- Lobby : [http://localhost:3002](http://localhost:3002)
- Catalog : [http://localhost:3003](http://localhost:3003)
- Cart : [http://localhost:3004](http://localhost:3004)

L'evaluation se fait depuis le Shell sur [http://localhost:3000](http://localhost:3000).

## Verification attendue

1. Ouvrir [http://localhost:3000](http://localhost:3000).
2. Dans le `Lobby`, cliquer sur `Rejoindre`.
3. Verifier que le badge notifications du `Header` augmente de `+1`.
4. Dans le `Catalog`, ajouter un produit au panier.
5. Verifier que le badge panier du `Header` affiche le bon nombre d'articles.
6. Dans le `Cart`, cliquer sur `Vider le panier`.
7. Verifier que le panier revient a `0` et que le badge du `Header` disparait quand le compteur vaut `0`.

## Fichier modifie pour le CP7

Le correctif demande par l'enonce a ete realise dans ce fichier :

- `pixelarena-checkpoint7/mfe-header/src/components/Navbar.jsx`

## Notes de correction

- un seul composant a ete modifie pour le CP7 : le `Navbar`
- le `cleanup` des abonnements est gere au `unmount`
- le repository contient aussi les checkpoints precedents, mais l'evaluation finale se fait sur `pixelarena-checkpoint7/`
