# Webtoon / Manga Color Automation App (Prototype)

Prototype d'une application desktop pour automatiser l'édition de webtoons/manga couleurs, avec une interface en **3 panels**:

1. **Détection & navigation des bulles/texte**
2. **Composition texte + styles**
3. **Vérification finale + export PSD**

## Démarrage rapide

```bash
python -m venv .venv
source .venv/bin/activate
pip install -e .
python -m webtoon_automation_app
```

## Fonctionnalités déjà incluses

- Interface PySide6 avec 3 onglets (panels) correspondant à votre workflow.
- Chargement d'un dossier d'images et navigation image par image.
- Détection **simulée** de zones texte/bulles (pipeline remplaçable).
- Sélection manuelle de zones (rectangles) dans l'image.
- Sauvegarde des zones (détectées + manuelles) dans un JSON par image.
- Panel de composition du texte:
  - taille, police, gras/italique,
  - couleur du texte,
  - contour simple (épaisseur + couleur),
  - règle de base "20% plus petit que la bulle" (suggestion auto).
- Panel de vérification finale:
  - aperçu des paramètres appliqués,
  - export de manifest JSON pour préparer un export PSD (stub).

## Limites actuelles (MVP)

- Détection OCR réelle (anglais/coréen) non branchée (placeholder).
- Rendu typographique avancé dans la bulle (forme harmonieuse multi-lignes) non finalisé.
- Export PSD réel non implémenté (manifest prêt pour intégration Photoshop/psd-tools/API).

## Prochaines étapes recommandées

1. Brancher un moteur de détection:
   - OCR: PaddleOCR / EasyOCR (EN + KO)
   - Détection bulles: segmentation (OpenCV + modèle dédié)
2. Ajouter un moteur de layout texte contraint par contour de bulle.
3. Intégrer export PSD:
   - via scripts Photoshop (JSX/Uxp),
   - ou génération PSD côté Python (selon exigences de calques/effets).
4. Ajouter presets de style par série/chapitre.

