# mesvisites-packs

Data packs for the **Mes Visites** app (the [mesvisites](https://github.com/BlashyrkhRavenDark/mesvisites) property-visit companion). The app downloads these SQLite files from the rolling [`packs-latest`](../../releases/tag/packs-latest) release: `common.sqlite` (commune index, SSMSI crime, schools with quality) plus one `dept_<D>.sqlite` per department (DVF sales, carte scolaire, INSEE BPE amenities), all listed by `manifest.json`.

Everything here is derived from French open data, redistributed under the corresponding open licences (Licence Ouverte / Etalab):

- [DVF — Demandes de valeurs foncières](https://www.data.gouv.fr/datasets/demandes-de-valeurs-foncieres) (DGFiP)
- [SSMSI — bases communales de la délinquance enregistrée](https://www.data.gouv.fr/datasets/bases-communales-de-la-delinquance-enregistree-par-la-police-et-la-gendarmerie-nationales/) (Ministère de l'Intérieur)
- [Éducation nationale — open data](https://data.education.gouv.fr) (annuaire, résultats, IPS, carte scolaire)
- [INSEE — Base permanente des équipements](https://www.insee.fr/fr/statistiques/8217525)

The packs contain aggregate and public transaction records only, are not search-engine material, and must not be used to re-identify persons (cf. LPF art. R*112 A-3). Alsace-Moselle (57/68) is absent because DVF does not cover the Livre foncier. DVF years 2016–2025. Rebuilt by `pipeline/build_app_packs.py` in the main repo and re-published with:

```
gh release upload packs-latest data/packs/* --clobber -R BlashyrkhRavenDark/mesvisites-packs
```
