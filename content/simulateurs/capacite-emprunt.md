---
title: "Calcul capacité d'emprunt : simulateur gratuit 2026"
description: "Calculez votre capacité d'emprunt immobilier en 2 minutes. Simulateur gratuit selon le HCSF (35 % d'endettement), avec apport, co-emprunteur et durée."
translationKey: "sim-capacite"
layout: "simulator"
lastmod: 2026-04-30
faq:
  - question: "Comment se calcule la capacité d'emprunt ?"
    answer: "La capacité d'emprunt correspond au capital maximal qu'une banque accepte de prêter sans dépasser le taux d'endettement légal de 35 pour cent (HCSF). On part de la somme des revenus nets, on soustrait les charges récurrentes, on multiplie par 0,35 pour obtenir la mensualité maximale, puis on convertit cette mensualité en capital sur la durée et le taux du prêt."
  - question: "Quel salaire pour emprunter 200 000 euros ?"
    answer: "Pour emprunter 200 000 euros sur 20 ans à 3,5 pour cent, sans charges et sans apport, il faut une mensualité d'environ 1 160 euros, soit un revenu net mensuel d'environ 3 320 euros. Avec un crédit auto de 300 euros par mois, le revenu nécessaire passe à 3 620 euros environ. La durée et l'apport modulent fortement ce seuil."
  - question: "Quelle est la différence entre capacité d'emprunt et capacité d'achat ?"
    answer: "La capacité d'emprunt est le montant que la banque accepte de prêter. La capacité d'achat correspond au prix maximal du bien finançable, soit la capacité d'emprunt plus l'apport personnel, moins les frais d'acquisition (frais de notaire, frais de garantie, frais de dossier). C'est cette dernière qui fixe le plafond de votre recherche immobilière."
  - question: "Quels revenus sont pris en compte par la banque ?"
    answer: "Les banques retiennent à 100 pour cent les salaires en CDI hors période d'essai, les pensions de retraite et les revenus fonciers stabilisés (souvent pondérés à 70 ou 80 pour cent). Les primes variables, dividendes et revenus indépendants sont moyennés sur 2 à 3 ans. Les allocations sociales (CAF, RSA) sont rarement intégrées."
  - question: "Comment augmenter sa capacité d'emprunt ?"
    answer: "Cinq leviers : solder un crédit conso pour libérer du taux d'endettement, augmenter l'apport personnel (10 à 20 pour cent recommandés), allonger la durée du prêt jusqu'à 25 ans, optimiser l'assurance emprunteur en délégation externe, et mobiliser un prêt aidé (PTZ, Action Logement, PAS) qui ne pèse pas sur le taux d'endettement."
---

Combien pouvez-vous emprunter pour votre projet immobilier ? Le montant maximum dépend de vos revenus, de vos charges et du plafond légal de 35 pour cent d'endettement fixé par le HCSF depuis 2022. Notre simulateur estime votre capacité d'emprunt en quelques secondes, avec ou sans co-emprunteur, en tenant compte de votre apport et de la durée du prêt visée.

<div class="simulator-card">
<form id="sim-capacite" class="simulator-form">

  <div class="sim-field sim-field-full">
    <label>Composition du foyer</label>
    <div class="sim-toggle" role="radiogroup" aria-label="Composition du foyer">
      <input type="radio" name="composition" id="comp-seul" value="seul" checked>
      <label for="comp-seul">Seul</label>
      <input type="radio" name="composition" id="comp-deux" value="deux">
      <label for="comp-deux">À deux</label>
    </div>
  </div>

  <div class="sim-field">
    <label for="revenus">Revenus nets mensuels (€)</label>
    <input type="number" id="revenus" min="0" step="100" value="3500" required>
  </div>
  <div class="sim-field" id="field-revenus2" hidden>
    <label for="revenus2">Revenus du co-emprunteur (€)</label>
    <input type="number" id="revenus2" min="0" step="100" value="0">
  </div>

  <div class="sim-field">
    <label for="charges">Charges mensuelles (crédits, pensions) (€)</label>
    <input type="number" id="charges" min="0" step="50" value="0">
  </div>
  <div class="sim-field">
    <label for="apport">Apport personnel (€)</label>
    <input type="number" id="apport" min="0" step="1000" value="0">
  </div>

  <div class="sim-field sim-field-full">
    <label>Durée du prêt</label>
    <div class="sim-toggle sim-toggle-duration" role="radiogroup" aria-label="Durée du prêt">
      <input type="radio" name="duree" id="d10" value="10">
      <label for="d10">10 ans</label>
      <input type="radio" name="duree" id="d15" value="15">
      <label for="d15">15 ans</label>
      <input type="radio" name="duree" id="d20" value="20" checked>
      <label for="d20">20 ans</label>
      <input type="radio" name="duree" id="d25" value="25">
      <label for="d25">25 ans</label>
    </div>
  </div>

  <div class="sim-field">
    <label for="taux">Taux d'intérêt annuel (%)</label>
    <input type="number" id="taux" min="0" max="15" step="0.1" value="3.5" required>
  </div>

  <button type="submit" class="btn-primary">Calculer ma capacité</button>
</form>

<div id="sim-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Capacité d'emprunt</span>
    <span class="sim-result-value" id="result-montant">—</span>
  </div>
  <div class="sim-result-main sim-result-secondary">
    <span class="sim-result-label">Capacité d'achat (capital + apport)</span>
    <span class="sim-result-value-small" id="result-achat">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Mensualité maximale : <strong id="result-mensualite">—</strong></li>
    <li>Coût total des intérêts : <strong id="result-cout">—</strong></li>
    <li>Taux d'endettement appliqué : <strong>35 %</strong></li>
  </ul>
  <p class="sim-disclaimer">Estimation indicative. Seule une banque peut confirmer votre capacité réelle après étude de dossier.</p>
</div>
</div>

> **L'essentiel à retenir :**
> 1. La capacité d'emprunt est plafonnée par le taux d'endettement légal de 35 pour cent fixé par le HCSF.
> 2. Un apport personnel de 10 à 20 pour cent est attendu par la majorité des banques en 2026.
> 3. Allonger la durée du prêt augmente le capital empruntable mais alourdit le coût total des intérêts.
> 4. Solder un crédit conso libère immédiatement de la marge sur le taux d'endettement.

## Comment se calcule votre capacité d'emprunt ?

Le calcul s'appuie sur la règle des 35 pour cent d'endettement maximum, fixée par le Haut Conseil de Stabilité Financière (HCSF) depuis janvier 2022. La banque déduit d'abord les charges récurrentes des revenus nets, applique le taux de 35 pour cent pour fixer la mensualité maximale, puis convertit cette mensualité en capital empruntable selon la durée et le taux d'intérêt du prêt.

La formule appliquée :

1. Mensualité maximale = (revenus nets - charges) × 35 %
2. Capital empruntable = mensualité × (1 - (1 + taux mensuel)^(-mois)) / taux mensuel

### Quels revenus sont pris en compte ?

- Les salaires en CDI hors période d'essai, retenus à 100 pour cent.
- Les pensions de retraite et les rentes viagères, retenues à 100 pour cent.
- Les revenus fonciers stabilisés, pondérés à 70 ou 80 pour cent selon la banque.
- Les revenus d'indépendants, moyennés sur 2 à 3 derniers exercices.
- Les primes et variables, lissés sur les 2 ou 3 dernières années.
- Les allocations sociales (CAF, RSA) ne sont pas intégrées par la majorité des banques.

### Quelles charges intègrent le calcul ?

- Les mensualités de crédits en cours (immobilier locatif, auto, conso).
- Les pensions alimentaires versées.
- Les loyers en cas de double résidence.
- Les charges fixes locatives ne sont pas comptées si l'achat met fin à la location.

## Quel emprunt selon votre salaire ?

Le tableau ci-dessous donne une estimation de la capacité d'emprunt pour une personne seule, sans charges ni apport, à un taux de 3,5 pour cent en 2026.

| Salaire net mensuel | 15 ans | 20 ans | 25 ans |
|---|---|---|---|
| 1 500 € | 73 400 € | 90 500 € | 104 900 € |
| 2 000 € | 97 900 € | 120 700 € | 139 800 € |
| 2 500 € | 122 400 € | 150 900 € | 174 800 € |
| 3 000 € | 146 900 € | 181 000 € | 209 700 € |
| 3 500 € | 171 400 € | 211 200 € | 244 700 € |
| 4 000 € | 195 800 € | 241 400 € | 279 700 € |
| 5 000 € | 244 800 € | 301 700 € | 349 600 € |
| 6 000 € | 293 800 € | 362 100 € | 419 500 € |

Ces montants supposent un dossier sans charges récurrentes. Chaque tranche de 100 euros de crédit en cours retire environ 17 000 euros de capacité empruntable sur 20 ans.

## Deux exemples concrets de calcul

> "Le respect de la règle des 35 pour cent d'endettement, assurance comprise, conditionne 96 pour cent des dossiers acceptés en 2025."
> — Haut Conseil de Stabilité Financière, rapport annuel 2025

Exemple 1, couple sans crédit en cours.

- Revenus nets cumulés : 4 000 € par mois.
- Charges : 0 €.
- Mensualité maximale : 4 000 × 35 % = 1 400 €.
- Capacité d'emprunt sur 20 ans à 3,5 % : environ 241 400 €.

Exemple 2, couple avec un crédit auto en cours.

- Revenus nets cumulés : 4 000 € par mois.
- Charges : 300 € de crédit auto.
- Mensualité maximale : (4 000 - 300) × 35 % = 1 295 €.
- Capacité d'emprunt sur 20 ans à 3,5 % : environ 223 200 €.

Le crédit auto fait perdre environ 18 000 euros de capacité d'emprunt, malgré un poids mensuel de seulement 300 euros.

## Capacité d'emprunt et capacité d'achat

Les deux notions sont souvent confondues mais ne mesurent pas la même chose.

- La capacité d'emprunt est le capital que la banque accepte de prêter.
- La capacité d'achat est le prix maximal du bien finançable. Elle ajoute l'apport personnel à la capacité d'emprunt et retranche les frais d'acquisition (notaire, garantie, dossier).

Pour un couple avec une capacité d'emprunt de 240 000 euros et un apport de 30 000 euros, la capacité d'achat brute est de 270 000 euros. En retirant environ 22 000 euros de [frais de notaire](/simulateurs/frais-notaire/) sur l'ancien et 2 000 euros de frais bancaires, le budget d'achat réel se situe autour de 246 000 euros.

## Les critères qui pèsent sur la décision bancaire

Au-delà de la règle des 35 pour cent, plusieurs critères qualitatifs orientent la réponse de la banque.

- **Apport personnel** : 10 à 20 pour cent du prix recommandés en 2026, pour couvrir les frais d'acquisition et rassurer la banque.
- **Stabilité professionnelle** : CDI hors période d'essai, fonctionnaire ou indépendant avec 3 bilans positifs.
- **Reste à vivre** : la banque vérifie qu'il reste au moins 700 à 1 000 euros par adulte du foyer après mensualité.
- **Âge en fin de prêt** : la majorité des banques exigent un remboursement avant 75 ou 80 ans.
- **Saut de charge** : un nouveau dossier dont la mensualité dépasse de plus de 50 pour cent l'ancien loyer fragilise la décision.
- **Historique bancaire** : absence de découvert récurrent, pas d'incident de paiement sur 12 mois.

## Comment augmenter votre capacité d'emprunt ?

Cinq leviers sont mobilisables avant la demande de prêt.

1. **Solder un crédit conso** : chaque tranche de 100 euros de mensualité libérée se transforme en environ 17 000 euros de capacité supplémentaire sur 20 ans à 3,5 pour cent.
2. **Augmenter l'apport personnel** : épargne PEL, livret A, donations familiales défiscalisées jusqu'à 100 000 euros par parent et par enfant tous les 15 ans.
3. **Allonger la durée du prêt** : passer de 20 à 25 ans gagne 16 à 17 pour cent de capacité, mais alourdit le coût total des intérêts.
4. **Optimiser l'assurance emprunteur** : la délégation externe permet d'économiser jusqu'à 50 pour cent du coût de l'assurance, ce qui réintègre du taux d'endettement.
5. **Mobiliser un prêt aidé** : le PTZ et le prêt Action Logement viennent compléter le prêt principal sans peser sur le taux d'endettement.

## Les prêts aidés à mobiliser

Plusieurs dispositifs publics complètent le prêt principal sans alourdir l'endettement.

- **Prêt à Taux Zéro (PTZ)** : depuis le 1er avril 2025 et jusqu'au 31 décembre 2027, accessible partout en France, finance jusqu'à 50 pour cent du bien selon la zone et le foyer (plafond 180 000 € dans le neuf).
- **Prêt Action Logement** : jusqu'à 30 000 euros à 1 pour cent pour les salariés du privé.
- **Prêt à l'Accession Sociale (PAS)** : conditions de revenus, ouvre droit aux APL accession et à des frais réduits.
- **Prêt conventionné** : taux plafonné, sans condition de ressources, ouvre l'éligibilité aux APL.

Pour aller plus loin sur le financement, consultez nos guides [stratégies de financement immobilier](/blog/financement-credit-immobilier/) et [investissement immobilier dans le neuf](/blog/comment-investir-dans-immobilier/). Avant de signer, simulez aussi vos [mensualités de prêt](/simulateurs/mensualites/) sur la durée retenue, chiffrez les [frais de notaire](/simulateurs/frais-notaire/) à intégrer au budget, et testez votre éligibilité au [simulateur prêt à taux zéro](/simulateurs/pret-taux-zero/). Pour arbitrer en amont, voyez notre [comparatif acheter ou louer](/blog/acheter-ou-louer-comparatif/) et la [checklist achat maison](/blog/achat-maison-checklist/).

## Questions fréquentes

<details>
<summary>Comment se calcule la capacité d'emprunt ?</summary>

La capacité d'emprunt correspond au capital maximal qu'une banque accepte de prêter sans dépasser le taux d'endettement légal de 35 pour cent (HCSF). On part de la somme des revenus nets, on soustrait les charges récurrentes, on multiplie par 0,35 pour obtenir la mensualité maximale, puis on convertit cette mensualité en capital sur la durée et le taux du prêt.

</details>

<details>
<summary>Quel salaire pour emprunter 200 000 euros ?</summary>

Pour emprunter 200 000 euros sur 20 ans à 3,5 pour cent, sans charges et sans apport, il faut une mensualité d'environ 1 160 euros, soit un revenu net mensuel d'environ 3 320 euros. Avec un crédit auto de 300 euros par mois, le revenu nécessaire passe à 3 620 euros environ. La durée et l'apport modulent fortement ce seuil.

</details>

<details>
<summary>Quelle est la différence entre capacité d'emprunt et capacité d'achat ?</summary>

La capacité d'emprunt est le montant que la banque accepte de prêter. La capacité d'achat correspond au prix maximal du bien finançable, soit la capacité d'emprunt plus l'apport personnel, moins les frais d'acquisition (frais de notaire, frais de garantie, frais de dossier). C'est cette dernière qui fixe le plafond de votre recherche immobilière.

</details>

<details>
<summary>Quels revenus sont pris en compte par la banque ?</summary>

Les banques retiennent à 100 pour cent les salaires en CDI hors période d'essai, les pensions de retraite et les revenus fonciers stabilisés (souvent pondérés à 70 ou 80 pour cent). Les primes variables, dividendes et revenus indépendants sont moyennés sur 2 à 3 ans. Les allocations sociales (CAF, RSA) sont rarement intégrées.

</details>

<details>
<summary>Comment augmenter sa capacité d'emprunt ?</summary>

Cinq leviers : solder un crédit conso pour libérer du taux d'endettement, augmenter l'apport personnel (10 à 20 pour cent recommandés), allonger la durée du prêt jusqu'à 25 ans, optimiser l'assurance emprunteur en délégation externe, et mobiliser un prêt aidé (PTZ, Action Logement, PAS) qui ne pèse pas sur le taux d'endettement.

</details>

<style>
.sim-toggle {
  display: flex;
  gap: 0;
  border: 1px solid var(--border);
  border-radius: var(--radius-md);
  background: var(--background);
  overflow: hidden;
  width: fit-content;
}
.sim-toggle input[type="radio"] {
  position: absolute;
  opacity: 0;
  pointer-events: none;
}
.sim-toggle label {
  font-family: var(--font-ui);
  font-size: 0.9rem;
  font-weight: 500;
  padding: 0.55rem 1rem;
  cursor: pointer;
  border-right: 1px solid var(--border);
  transition: background 0.2s, color 0.2s;
  color: var(--text);
  background: transparent;
  margin: 0;
}
.sim-toggle label:last-of-type { border-right: none; }
.sim-toggle input[type="radio"]:checked + label {
  background: var(--primary);
  color: var(--white, #fff);
}
.sim-toggle-duration { width: 100%; }
.sim-toggle-duration label { flex: 1; text-align: center; }
.sim-field-full { grid-column: 1 / -1; }
.sim-result-secondary { margin-top: 0.6rem; padding-top: 0.6rem; border-top: 1px dashed var(--border); }
.sim-result-value-small {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--primary);
  font-style: italic;
}
@media (max-width: 600px) {
  .sim-toggle-duration { flex-wrap: wrap; }
  .sim-toggle-duration label { flex: 1 1 50%; border-bottom: 1px solid var(--border); }
}
</style>

<script>
(function() {
  var form = document.getElementById('sim-capacite');
  if (!form) return;

  var compRadios = form.querySelectorAll('input[name="composition"]');
  var fieldRev2 = document.getElementById('field-revenus2');
  compRadios.forEach(function(r) {
    r.addEventListener('change', function() {
      if (this.value === 'deux' && this.checked) {
        fieldRev2.hidden = false;
      } else if (this.value === 'seul' && this.checked) {
        fieldRev2.hidden = true;
        document.getElementById('revenus2').value = 0;
      }
    });
  });

  form.addEventListener('submit', function(e) {
    e.preventDefault();
    var revenus1 = parseFloat(document.getElementById('revenus').value) || 0;
    var revenus2 = parseFloat(document.getElementById('revenus2').value) || 0;
    var charges = parseFloat(document.getElementById('charges').value) || 0;
    var apport = parseFloat(document.getElementById('apport').value) || 0;
    var dureeEl = form.querySelector('input[name="duree"]:checked');
    var duree = dureeEl ? parseInt(dureeEl.value, 10) : 20;
    var taux = parseFloat(document.getElementById('taux').value) || 0;

    var revenus = revenus1 + revenus2;
    var mensualite = Math.max(0, (revenus - charges) * 0.35);
    var mois = duree * 12;
    var tauxM = taux / 100 / 12;
    var capital = tauxM > 0 ? mensualite * (1 - Math.pow(1 + tauxM, -mois)) / tauxM : mensualite * mois;
    var cout = mensualite * mois - capital;
    var capaciteAchat = capital + apport;

    var fmt = new Intl.NumberFormat('fr-FR', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
    document.getElementById('result-montant').textContent = fmt.format(capital);
    document.getElementById('result-achat').textContent = fmt.format(capaciteAchat);
    document.getElementById('result-mensualite').textContent = fmt.format(mensualite);
    document.getElementById('result-cout').textContent = fmt.format(Math.max(0, cout));
    document.getElementById('sim-result').hidden = false;
  });
})();
</script>
