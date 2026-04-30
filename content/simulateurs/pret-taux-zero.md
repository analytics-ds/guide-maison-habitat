---
title: "Simulateur prêt à taux zéro (PTZ) : calcul gratuit 2026"
description: "Calculez votre PTZ 2026 selon la zone, vos revenus, la composition du foyer et le type de bien. Réforme 2025-2027 intégrée, plafonds officiels à jour."
translationKey: "sim-ptz"
layout: "simulator"
lastmod: 2026-04-30
faq:
  - question: "Qui peut bénéficier du prêt à taux zéro en 2026 ?"
    answer: "Le PTZ est réservé aux primo-accédants, c'est-à-dire aux ménages qui n'ont pas été propriétaires de leur résidence principale au cours des 2 dernières années. Trois cas dérogatoires : situation de handicap, sinistre rendant le logement inhabitable, et titulaire d'une carte mobilité inclusion. Le bien acheté doit devenir la résidence principale dans l'année suivant l'acquisition."
  - question: "Quels biens sont éligibles au PTZ après la réforme du 1er avril 2025 ?"
    answer: "Depuis le 1er avril 2025 et jusqu'au 31 décembre 2027, le PTZ est accessible partout en France pour le neuf collectif (appartement) et le neuf individuel (maison) sous conditions de performance énergétique, ainsi que pour l'ancien avec au moins 25 pour cent de travaux de rénovation en zones B2 et C, et le logement social ancien."
  - question: "Quels sont les plafonds de ressources PTZ en 2026 ?"
    answer: "Les plafonds 2025-2026 dépendent de la zone et du nombre de personnes au foyer. En zone A et A bis, ils vont de 49 000 euros pour 1 personne à 161 700 euros à partir de 8 personnes. En zone B2 et C, ils vont de 31 500 à 103 950 euros. La banque retient le revenu fiscal de référence N-2 ou le coût total de l'opération divisé par 9 si plus élevé."
  - question: "Comment se calcule le montant du PTZ ?"
    answer: "Le montant retenu est égal au prix du bien (plafonné selon la zone et la composition du foyer) multiplié par une quotité variable selon votre tranche de revenu (T1 à T4) et le type de bien. La quotité oscille entre 10 et 50 pour cent. En neuf collectif, les ménages les plus modestes peuvent obtenir jusqu'à 50 pour cent de leur projet en PTZ, dans la limite des plafonds d'opération."
  - question: "Comment se rembourse le PTZ ?"
    answer: "Le PTZ se rembourse en 2 périodes après une phase de différé total où aucune mensualité n'est due. Le différé dure 5, 10 ou 15 ans selon la tranche de revenu, puis le remboursement s'étale sur 10 à 15 ans supplémentaires. La durée totale est de 20 à 25 ans selon votre profil. Les ménages les plus modestes bénéficient du différé le plus long."
---

Le prêt à taux zéro est un prêt sans intérêts accordé par l'État aux primo-accédants pour financer une partie de leur résidence principale. Depuis le 1er avril 2025, il est accessible partout en France et jusqu'au 31 décembre 2027, avec une éligibilité élargie aux maisons neuves. Notre simulateur estime votre montant PTZ en quelques secondes, en intégrant les plafonds de ressources, les plafonds d'opération et les quotités officielles 2025-2026.

<div class="simulator-card">
<form id="sim-ptz" class="simulator-form">

  <div class="sim-field sim-field-full">
    <label>Avez-vous été propriétaire de votre résidence principale au cours des 2 dernières années ?</label>
    <div class="sim-toggle" role="radiogroup" aria-label="Statut primo-accédant">
      <input type="radio" name="proprio" id="prop-non" value="non" checked>
      <label for="prop-non">Non</label>
      <input type="radio" name="proprio" id="prop-oui" value="oui">
      <label for="prop-oui">Oui</label>
    </div>
  </div>

  <div class="sim-field">
    <label for="p-revenu">Revenu fiscal de référence N-2 (€/an)</label>
    <input type="number" id="p-revenu" min="0" step="500" value="40000" required>
  </div>
  <div class="sim-field">
    <label for="p-personnes">Nombre de personnes du foyer</label>
    <input type="number" id="p-personnes" min="1" max="8" step="1" value="2" required>
  </div>

  <div class="sim-field">
    <label for="p-zone">Zone géographique</label>
    <select id="p-zone" required>
      <option value="A">Zone A bis / A (Paris et grandes villes tendues)</option>
      <option value="B1" selected>Zone B1 (agglomérations 250 000+ habitants)</option>
      <option value="B2">Zone B2 (villes moyennes)</option>
      <option value="C">Zone C (zones détendues)</option>
    </select>
  </div>
  <div class="sim-field">
    <label for="p-type">Type de bien</label>
    <select id="p-type" required>
      <option value="neuf_collectif">Neuf collectif (appartement)</option>
      <option value="neuf_individuel">Neuf individuel (maison)</option>
      <option value="ancien">Ancien avec 25 % de travaux (B2 et C)</option>
      <option value="hlm_ancien">Logement social ancien</option>
    </select>
  </div>

  <div class="sim-field">
    <label for="p-prix">Prix du bien (€)</label>
    <input type="number" id="p-prix" min="0" step="1000" value="250000" required>
  </div>
  <div class="sim-field">
    <label for="p-apport">Apport personnel (€)</label>
    <input type="number" id="p-apport" min="0" step="1000" value="0">
  </div>

  <button type="submit" class="btn-primary">Calculer mon PTZ</button>
</form>

<div id="sim-p-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Montant PTZ estimé</span>
    <span class="sim-result-value" id="p-result-montant">—</span>
  </div>
  <div class="sim-result-main sim-result-secondary">
    <span class="sim-result-label">Reste à financer (hors apport et frais)</span>
    <span class="sim-result-value-small" id="p-result-reste">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Tranche de revenu : <strong id="p-result-tranche">—</strong></li>
    <li>Plafond d'opération retenu : <strong id="p-result-plafond">—</strong></li>
    <li>Quotité PTZ appliquée : <strong id="p-result-quotite">—</strong></li>
    <li>Durée totale estimée : <strong id="p-result-duree">—</strong></li>
    <li>Période de différé : <strong id="p-result-differe">—</strong></li>
  </ul>
  <p class="sim-disclaimer">Estimation indicative basée sur le barème officiel 2025-2026. Le PTZ est soumis à des conditions précises à vérifier auprès d'une banque conventionnée par l'État.</p>
</div>

<div id="sim-p-non-eligible" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Éligibilité PTZ</span>
    <span class="sim-result-value" style="color:#a14a4a">Non éligible</span>
  </div>
  <p id="p-result-raison" class="sim-disclaimer"></p>
  <p class="sim-disclaimer">Cette estimation se base sur les règles standards. Des cas dérogatoires existent (handicap, sinistre, mobilité inclusion). Vérifiez votre situation auprès d'une banque conventionnée.</p>
</div>
</div>

> **L'essentiel à retenir :**
> 1. Le PTZ est un prêt sans intérêts, réservé aux primo-accédants pour leur résidence principale.
> 2. Depuis le 1er avril 2025, il est accessible partout en France pour le neuf collectif et le neuf individuel.
> 3. Son montant dépend de la zone, du nombre de personnes au foyer, du type de bien et de la tranche de revenu (T1 à T4).
> 4. Le remboursement débute après une période de différé de 5, 10 ou 15 ans, sur une durée totale de 20 à 25 ans.

## Qu'est-ce que le prêt à taux zéro ?

Le prêt à taux zéro, ou PTZ, est un prêt aidé par l'État, accordé sans intérêts ni frais de dossier. Créé en 1995 pour faciliter l'accession à la propriété, il s'adresse aux ménages aux revenus intermédiaires et modestes qui achètent leur première résidence principale. Il ne finance jamais l'intégralité du projet : il vient compléter un prêt immobilier classique et un éventuel apport personnel.

Le PTZ est distribué uniquement par les banques conventionnées par l'État. Le bien financé doit devenir la résidence principale du ménage dans l'année qui suit l'acquisition, et le rester pendant au moins 6 ans (sauf cas dérogatoires).

## PTZ 2026 : la réforme du 1er avril 2025

La loi de finances pour 2025 a profondément remanié le PTZ avec une réforme entrée en vigueur le 1er avril 2025 et applicable jusqu'au 31 décembre 2027. Quatre changements majeurs.

- Le PTZ est désormais accessible partout en France pour le neuf collectif (appartement) et le neuf individuel (maison), alors qu'il était auparavant réservé aux zones B2 et C pour la maison neuve.
- La quotité maximale passe à 50 pour cent du prix du bien pour les ménages les plus modestes en neuf collectif.
- Les plafonds d'opération sont actualisés (jusqu'à 360 000 euros en zone A pour 5 personnes ou plus).
- Les conditions de performance énergétique du bien neuf sont renforcées (RE2020).

## Qui peut bénéficier du PTZ ?

L'éligibilité repose sur deux conditions principales : la primo-accession et le respect des plafonds de ressources.

### Primo-accédants

Le PTZ est réservé aux ménages qui n'ont pas été propriétaires de leur résidence principale au cours des 2 années précédant l'offre de prêt. Posséder une résidence secondaire ou un investissement locatif n'empêche pas l'éligibilité.

### Cas dérogatoires

Trois situations permettent de bénéficier du PTZ même en ayant été propriétaire récemment.

- Titulaire d'une carte mobilité inclusion mention "invalidité".
- Bénéficiaire de l'allocation aux adultes handicapés ou de l'allocation d'éducation de l'enfant handicapé.
- Sinistre ayant rendu le logement définitivement inhabitable (catastrophe naturelle, technologique).

## Quels biens sont éligibles au PTZ ?

Quatre catégories de biens ouvrent droit au PTZ depuis la réforme 2025.

### Le neuf collectif

Tout appartement neuf, en VEFA ou en construction, est éligible partout en France, dans toutes les zones (A, A bis, B1, B2, C). C'est le principal segment couvert par la réforme 2025.

### Le neuf individuel

Les maisons individuelles neuves sont désormais éligibles partout, sous condition de respect de la RE2020. Avant la réforme, elles n'étaient éligibles qu'en zones B2 et C avec une quotité réduite.

### L'ancien avec 25 % de travaux

Un logement ancien éligible au PTZ doit faire l'objet de travaux d'amélioration représentant au moins 25 pour cent du coût total de l'opération. Cette voie reste réservée aux zones B2 et C, avec une obligation de gain énergétique après travaux.

### Le logement social ancien

L'achat d'un logement HLM par son locataire (vente HLM) ouvre droit au PTZ, à un taux réduit (10 pour cent du prix). Il s'agit d'une voie spécifique destinée à favoriser l'accession sociale.

## Plafonds de ressources PTZ 2026

Le revenu fiscal de référence N-2 du foyer ne doit pas dépasser les seuils suivants. À défaut, c'est le coût total de l'opération divisé par 9 qui est retenu pour la comparaison, si ce montant est supérieur.

| Personnes | Zone A et A bis | Zone B1 | Zone B2 et C |
|---|---|---|---|
| 1 | 49 000 € | 34 500 € | 31 500 € |
| 2 | 73 500 € | 51 750 € | 47 250 € |
| 3 | 88 200 € | 62 100 € | 56 700 € |
| 4 | 102 900 € | 72 450 € | 66 150 € |
| 5 | 117 600 € | 82 800 € | 75 600 € |
| 6 | 132 300 € | 93 150 € | 85 050 € |
| 7 | 147 000 € | 103 500 € | 94 500 € |
| 8 et + | 161 700 € | 113 850 € | 103 950 € |

## Plafonds d'opération PTZ 2026

Le PTZ ne s'applique pas sur la totalité du prix du bien, mais dans la limite d'un plafond d'opération qui dépend de la zone et de la composition du foyer.

| Personnes | Zone A et A bis | Zone B1 | Zone B2 | Zone C |
|---|---|---|---|---|
| 1 | 150 000 € | 135 000 € | 110 000 € | 100 000 € |
| 2 | 225 000 € | 202 500 € | 165 000 € | 150 000 € |
| 3 | 270 000 € | 243 000 € | 198 000 € | 180 000 € |
| 4 | 315 000 € | 283 500 € | 231 000 € | 210 000 € |
| 5 et + | 360 000 € | 324 000 € | 264 000 € | 240 000 € |

## Comment se calcule le montant du PTZ ?

Le montant du PTZ s'obtient en deux étapes.

1. On retient comme base de calcul le minimum entre le prix du bien et le plafond d'opération applicable selon la zone et le nombre de personnes.
2. On applique à cette base une quotité (pourcentage) qui dépend de la tranche de revenu (T1 à T4) du ménage et du type de bien.

Les quotités après réforme 2025, pour les ménages relevant des tranches T1 et T2, atteignent 50 pour cent du plafond en neuf collectif, ce qui peut représenter jusqu'à 180 000 euros de PTZ pour un ménage modeste en zone A. Pour les ménages les plus aisés (T4), la quotité tombe à 10 ou 20 pour cent selon le type de bien.

> "L'élargissement du PTZ aux maisons neuves dans toutes les zones constitue le changement le plus structurant pour les primo-accédants depuis 2018."
> — Ministère du Logement, communiqué de mars 2025

Pour calibrer votre projet d'achat, simulez d'abord votre [capacité d'emprunt](/simulateurs/capacite-emprunt/) puis vos [mensualités de prêt](/simulateurs/mensualites/) sur le prêt principal qui complétera le PTZ.

## Comment se rembourse le PTZ ?

Le remboursement du PTZ se déroule en 2 périodes successives, après une phase de différé total où aucune mensualité n'est due.

- Période de différé : 5, 10 ou 15 ans selon la tranche de revenu (T4 à T1). Pendant cette phase, le prêt principal se rembourse seul.
- Période 1 : remboursement du capital PTZ sans intérêts, sur 10 à 15 ans.
- La durée totale (différé + remboursement) varie de 20 ans pour les profils T4 à 25 ans pour les profils T1.

Cette structure en deux temps permet d'alléger les mensualités cumulées en début de projet, période où l'emprunteur supporte aussi les frais d'acquisition et l'aménagement du bien.

## Comment obtenir le PTZ ?

Le PTZ ne peut être souscrit qu'auprès d'une banque conventionnée par l'État. La majorité des grandes banques françaises (Crédit Agricole, BNP Paribas, Société Générale, Banque Populaire, Caisse d'Épargne, LCL, Crédit Mutuel, Hello bank, CCF) sont conventionnées.

Le PTZ est toujours adossé à un prêt principal : il n'existe pas de financement immobilier 100 pour cent PTZ. Il est cumulable avec le prêt Action Logement, le prêt à l'accession sociale (PAS), un prêt épargne logement (PEL/CEL) et un prêt classique.

Pour aller plus loin sur le financement, consultez nos guides [stratégies de financement immobilier](/blog/financement-credit-immobilier/) et [investissement immobilier dans le neuf](/blog/comment-investir-dans-immobilier/). Avant de signer, chiffrez les [frais de notaire](/simulateurs/frais-notaire/) à intégrer au budget et parcourez les [points à vérifier avant l'achat](/blog/achat-maison-checklist/). Pour arbitrer en amont, voyez notre [comparatif acheter ou louer](/blog/acheter-ou-louer-comparatif/).

## Questions fréquentes

<details>
<summary>Qui peut bénéficier du prêt à taux zéro en 2026 ?</summary>

Le PTZ est réservé aux primo-accédants, c'est-à-dire aux ménages qui n'ont pas été propriétaires de leur résidence principale au cours des 2 dernières années. Trois cas dérogatoires : situation de handicap, sinistre rendant le logement inhabitable, et titulaire d'une carte mobilité inclusion. Le bien acheté doit devenir la résidence principale dans l'année suivant l'acquisition.

</details>

<details>
<summary>Quels biens sont éligibles au PTZ après la réforme du 1er avril 2025 ?</summary>

Depuis le 1er avril 2025 et jusqu'au 31 décembre 2027, le PTZ est accessible partout en France pour le neuf collectif (appartement) et le neuf individuel (maison) sous conditions de performance énergétique, ainsi que pour l'ancien avec au moins 25 pour cent de travaux de rénovation en zones B2 et C, et le logement social ancien.

</details>

<details>
<summary>Quels sont les plafonds de ressources PTZ en 2026 ?</summary>

Les plafonds 2025-2026 dépendent de la zone et du nombre de personnes au foyer. En zone A et A bis, ils vont de 49 000 euros pour 1 personne à 161 700 euros à partir de 8 personnes. En zone B2 et C, ils vont de 31 500 à 103 950 euros. La banque retient le revenu fiscal de référence N-2 ou le coût total de l'opération divisé par 9 si plus élevé.

</details>

<details>
<summary>Comment se calcule le montant du PTZ ?</summary>

Le montant retenu est égal au prix du bien (plafonné selon la zone et la composition du foyer) multiplié par une quotité variable selon votre tranche de revenu (T1 à T4) et le type de bien. La quotité oscille entre 10 et 50 pour cent. En neuf collectif, les ménages les plus modestes peuvent obtenir jusqu'à 50 pour cent de leur projet en PTZ, dans la limite des plafonds d'opération.

</details>

<details>
<summary>Comment se rembourse le PTZ ?</summary>

Le PTZ se rembourse en 2 périodes après une phase de différé total où aucune mensualité n'est due. Le différé dure 5, 10 ou 15 ans selon la tranche de revenu, puis le remboursement s'étale sur 10 à 15 ans supplémentaires. La durée totale est de 20 à 25 ans selon votre profil. Les ménages les plus modestes bénéficient du différé le plus long.

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
.sim-field-full { grid-column: 1 / -1; }
.sim-result-secondary { margin-top: 0.6rem; padding-top: 0.6rem; border-top: 1px dashed var(--border); }
.sim-result-value-small {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--primary);
  font-style: italic;
}
</style>

<script>
(function() {
  var form = document.getElementById('sim-ptz');
  if (!form) return;

  var plafondsRevenus = {
    A:  { 1: 49000, 2: 73500, 3: 88200, 4: 102900, 5: 117600, 6: 132300, 7: 147000, 8: 161700 },
    B1: { 1: 34500, 2: 51750, 3: 62100, 4: 72450, 5: 82800, 6: 93150, 7: 103500, 8: 113850 },
    B2: { 1: 31500, 2: 47250, 3: 56700, 4: 66150, 5: 75600, 6: 85050, 7: 94500, 8: 103950 },
    C:  { 1: 31500, 2: 47250, 3: 56700, 4: 66150, 5: 75600, 6: 85050, 7: 94500, 8: 103950 }
  };
  var plafondsOperation = {
    A:  { 1: 150000, 2: 225000, 3: 270000, 4: 315000, 5: 360000 },
    B1: { 1: 135000, 2: 202500, 3: 243000, 4: 283500, 5: 324000 },
    B2: { 1: 110000, 2: 165000, 3: 198000, 4: 231000, 5: 264000 },
    C:  { 1: 100000, 2: 150000, 3: 180000, 4: 210000, 5: 240000 }
  };
  var coeffFamille = { 1: 1, 2: 1.4, 3: 1.7, 4: 2, 5: 2.3, 6: 2.6, 7: 2.9, 8: 3.2 };
  var bornesTranches = {
    A:  [25000, 31000, 40000],
    B1: [21500, 26000, 32000],
    B2: [18000, 22000, 28000],
    C:  [15000, 19000, 24000]
  };
  var quotites = {
    neuf_collectif:  { T1: 0.50, T2: 0.40, T3: 0.40, T4: 0.30 },
    neuf_individuel: { T1: 0.30, T2: 0.20, T3: 0.20, T4: 0.10 },
    ancien:          { T1: 0.50, T2: 0.40, T3: 0.30, T4: 0.20 },
    hlm_ancien:      { T1: 0.10, T2: 0.10, T3: 0.10, T4: 0.10 }
  };
  var modalites = {
    T1: { duree: 25, differe: 15 },
    T2: { duree: 22, differe: 10 },
    T3: { duree: 22, differe: 10 },
    T4: { duree: 20, differe: 5 }
  };

  var fmt = new Intl.NumberFormat('fr-FR', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
  var resultEligible = document.getElementById('sim-p-result');
  var resultNon = document.getElementById('sim-p-non-eligible');
  var raison = document.getElementById('p-result-raison');

  function showNonEligible(msg) {
    resultEligible.hidden = true;
    raison.textContent = msg;
    resultNon.hidden = false;
  }

  form.addEventListener('submit', function(e) {
    e.preventDefault();
    var proprio = form.querySelector('input[name="proprio"]:checked').value === 'oui';
    if (proprio) {
      showNonEligible('Vous avez été propriétaire de votre résidence principale dans les 2 dernières années. Le PTZ est en principe réservé aux primo-accédants, sauf cas dérogatoires (handicap, sinistre).');
      return;
    }
    var personnes = Math.min(8, Math.max(1, parseInt(document.getElementById('p-personnes').value, 10) || 1));
    var zone = document.getElementById('p-zone').value;
    var revenu = parseFloat(document.getElementById('p-revenu').value) || 0;
    var prix = parseFloat(document.getElementById('p-prix').value) || 0;
    var apport = parseFloat(document.getElementById('p-apport').value) || 0;
    var type = document.getElementById('p-type').value;

    var plafondR = plafondsRevenus[zone][personnes];
    if (revenu > plafondR) {
      showNonEligible('Vos revenus (' + fmt.format(revenu) + ') dépassent le plafond PTZ pour votre zone et la composition du foyer (' + fmt.format(plafondR) + ').');
      return;
    }

    if ((type === 'ancien' || type === 'hlm_ancien') && (zone === 'A' || zone === 'B1')) {
      showNonEligible('Le PTZ pour l\'ancien avec travaux ou le logement social ancien est réservé aux zones B2 et C.');
      return;
    }

    var coeff = coeffFamille[personnes];
    var revenuRef = revenu / coeff;
    var bornes = bornesTranches[zone];
    var tranche = 'T4';
    if (revenuRef <= bornes[0]) tranche = 'T1';
    else if (revenuRef <= bornes[1]) tranche = 'T2';
    else if (revenuRef <= bornes[2]) tranche = 'T3';

    var quotite = quotites[type][tranche];
    var plafondOpKey = Math.min(personnes, 5);
    var plafondOp = plafondsOperation[zone][plafondOpKey];
    var base = Math.min(prix, plafondOp);
    var ptz = Math.round(base * quotite);
    var resteAFinancer = Math.max(0, prix - ptz - apport);
    var modalite = modalites[tranche];

    document.getElementById('p-result-montant').textContent = fmt.format(ptz);
    document.getElementById('p-result-reste').textContent = fmt.format(resteAFinancer);
    document.getElementById('p-result-tranche').textContent = tranche;
    document.getElementById('p-result-plafond').textContent = fmt.format(plafondOp);
    document.getElementById('p-result-quotite').textContent = (quotite * 100).toFixed(0) + ' %';
    document.getElementById('p-result-duree').textContent = modalite.duree + ' ans';
    document.getElementById('p-result-differe').textContent = modalite.differe + ' ans';
    resultNon.hidden = true;
    resultEligible.hidden = false;
  });
})();
</script>
