Voici un **README.md** prêt à coller dans ton dépôt.

---

# SHAP – Notebook d’explicabilité sur données de scoring

Petit projet démonstratif pour charger un jeu de données Excel de scoring, entraîner/évaluer un modèle (dans le notebook) et analyser les contributions locales/globales avec **SHAP**.

## Structure du projet

```
.
├── shap_venv/            # Environnement virtuel Python (optionnel, ne pas versionner)
├── README.md             # Ce fichier
├── requirements.txt      # Dépendances Python
├── Scoring_data.xlsx     # Jeu de données d’exemple (features + target)
└── shap.ipynb            # Notebook principal (chargement, modèle, SHAP)
```


## Prérequis

* Python ≥ 3.10
* `pip` et (optionnel) `virtualenv` / `venv`
* VS Code + extension **Jupyter** (recommandé)

## Installation rapide

### 1) Créer/activer l’environnement (recommandé)

**macOS / Linux**

```bash
python3 -m venv shap_venv
source shap_venv/bin/activate
```

**Windows (PowerShell)**

```powershell
python -m venv shap_venv
.\shap_venv\Scripts\Activate.ps1
```

### 2) Installer les dépendances

```bash
pip install -r requirements.txt
```

> Si tu charges des fichiers `.xlsx`, assure-toi que **openpyxl** est installé
> (il est listé dans `requirements.txt`). Sinon : `pip install openpyxl`.

### 3) (Optionnel) Lier la venv à Jupyter

```bash
python -m ipykernel install --user --name=shap_venv --display-name "Python (shap_venv)"
```

## Exécution

1. Ouvre le projet dans VS Code.
2. Sélectionne le kernel **Python (shap_venv)** dans le notebook si besoin.
3. Ouvre **`shap.ipynb`** et exécute les cellules de haut en bas.

Le notebook :

* charge `Scoring_data.xlsx` (onglet/feuille par défaut ; adapte le chemin/nom si nécessaire) ;
* prépare les données ;
* entraîne un modèle simple (ex. arbre/forêt/logistique selon le code du notebook) ;
* calcule les valeurs **SHAP** (globale + locale) et affiche des graphiques d’explicabilité.

## Personnalisation

* Remplace `Scoring_data.xlsx` par ton propre fichier en conservant la/les colonnes attendues par le notebook (features + cible).
* Mets à jour `requirements.txt` si tu ajoutes des bibliothèques :

  ```bash
  pip freeze > requirements.txt
  ```

## Dépannage

* **Le fichier Excel ne se charge pas** : vérifie la présence d’`openpyxl` et le nom de la **feuille** (`sheet_name`) si spécifié.
* **Kernel non détecté** : réinstalle le noyau Jupyter (voir étape 3) et relance VS Code.
* **Apple Silicon (M1/M2)** : certaines libs peuvent nécessiter les *Command Line Tools* (`xcode-select --install`).

## Contact

Créé par : Yoann Pull

---
