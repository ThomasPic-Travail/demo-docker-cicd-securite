\# Demo Docker CI/CD Sécurisé



Petit projet Flask conteneurisé avec pipeline CI/CD automatisé (GitHub Actions)

intégrant un scan de vulnérabilités via Trivy.



\## Ce que fait le pipeline

\- Build de l'image Docker à chaque push

\- Scan automatique des vulnérabilités (Trivy)

\- Blocage du pipeline si des failles CRITICAL/HIGH sont détectées



\## Résultat d'un test comparatif

\- Image `python:3.12-slim` (Test 2) : 57 vulnérabilités (3 CRITICAL, 54 HIGH)

\- Après upgrade des paquets système : 44 vulnérabilités (0 CRITICAL, 44 HIGH)

\- Image `python:3.12-alpine` (Test 3) : pipeline passe au vert, quasiment aucune vulnérabilité détectée



Conclusion : réduire la surface d'attaque en choisissant une image de base minimale

est plus efficace que de multiplier les correctifs sur une image lourde.

