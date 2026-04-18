---
title: "Simulateur de prêt à taux zéro (PTZ)"
description: "Estimez le montant de votre prêt à taux zéro (PTZ) selon la zone, le nombre de personnes au foyer et le prix du bien."
translationKey: "sim-ptz"
layout: "simulator"
---

Le **simulateur de prêt à taux zéro (PTZ)** estime le montant de cette aide sans intérêt, destinée aux primo-accédants qui achètent leur résidence principale.

<div class="simulator-card">
<form id="sim-ptz" class="simulator-form">
  <div class="sim-field">
    <label for="p-prix">Prix du bien (€)</label>
    <input type="number" id="p-prix" min="0" step="1000" value="250000" required>
  </div>
  <div class="sim-field">
    <label for="p-zone">Zone géographique</label>
    <select id="p-zone" required>
      <option value="A">Zone A bis / A (Paris et grandes villes tendues)</option>
      <option value="B1">Zone B1 (agglomérations 250 000+ habitants)</option>
      <option value="B2">Zone B2 (villes moyennes)</option>
      <option value="C">Zone C (zones détendues)</option>
    </select>
  </div>
  <div class="sim-field">
    <label for="p-personnes">Nombre de personnes au foyer</label>
    <input type="number" id="p-personnes" min="1" max="8" step="1" value="2" required>
  </div>
  <div class="sim-field">
    <label for="p-type">Type de bien</label>
    <select id="p-type" required>
      <option value="neuf">Neuf (VEFA, construction)</option>
      <option value="ancien">Ancien avec travaux (25 % min)</option>
    </select>
  </div>
  <button type="submit" class="btn-primary">Calculer</button>
</form>

<div id="sim-p-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Montant PTZ estimé</span>
    <span class="sim-result-value" id="p-result-montant">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Plafond d'opération retenu : <strong id="p-result-plafond">—</strong></li>
    <li>Quotité PTZ appliquée : <strong id="p-result-quotite">—</strong></li>
    <li>Reste à financer : <strong id="p-result-reste">—</strong></li>
  </ul>
  <p class="sim-disclaimer">Estimation indicative. Le PTZ est soumis à des conditions de ressources et d'éligibilité à vérifier auprès de votre banque.</p>
</div>
</div>

## Qu'est-ce que le PTZ

Le prêt à taux zéro (PTZ) est un prêt sans intérêts accordé par l'État pour aider les primo-accédants à acheter leur résidence principale. Il ne finance qu'une partie du projet (20 à 50 pour cent selon la zone et le profil) et vient en complément d'un prêt principal.

## Plafonds 2026

| Zone | Plafond opération (couple) | Quotité max |
|------|-----------------------------|--------------|
| A et A bis | 300 000 € | 50 % |
| B1 | 270 000 € | 40 % |
| B2 | 180 000 € | 40 % |
| C | 150 000 € | 40 % |

## Conditions d'éligibilité

- Être primo-accédant (pas propriétaire de sa résidence principale depuis 2 ans)
- Respecter les plafonds de ressources selon la zone
- Acheter dans le neuf ou l'ancien avec 25 % de travaux minimum
- En faire sa résidence principale pendant au moins 6 ans

Pour approfondir le financement, consultez notre [guide financement crédit immobilier](/blog/financement-credit-immobilier/) et notre [checklist achat maison](/blog/achat-maison-checklist/).

<script>
(function() {
  var form = document.getElementById('sim-ptz');
  if (!form) return;
  var plafonds = {
    A: { 1: 150000, 2: 225000, 3: 270000, 4: 315000, 5: 360000 },
    B1: { 1: 135000, 2: 202500, 3: 243000, 4: 283500, 5: 324000 },
    B2: { 1: 110000, 2: 165000, 3: 198000, 4: 231000, 5: 264000 },
    C: { 1: 100000, 2: 150000, 3: 180000, 4: 210000, 5: 240000 }
  };
  var quotites = { A: 0.50, B1: 0.40, B2: 0.40, C: 0.40 };
  form.addEventListener('submit', function(e) {
    e.preventDefault();
    var prix = parseFloat(document.getElementById('p-prix').value) || 0;
    var zone = document.getElementById('p-zone').value;
    var personnes = Math.min(5, Math.max(1, parseInt(document.getElementById('p-personnes').value, 10) || 1));
    var type = document.getElementById('p-type').value;
    var plafond = plafonds[zone][personnes] || plafonds[zone][5];
    var base = Math.min(prix, plafond);
    var quotite = quotites[zone];
    if (type === 'ancien') quotite = quotite * 0.8;
    var ptz = base * quotite;
    var reste = prix - ptz;
    var fmt = new Intl.NumberFormat('fr-FR', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
    document.getElementById('p-result-montant').textContent = fmt.format(ptz);
    document.getElementById('p-result-plafond').textContent = fmt.format(plafond);
    document.getElementById('p-result-quotite').textContent = (quotite * 100).toFixed(0) + ' %';
    document.getElementById('p-result-reste').textContent = fmt.format(Math.max(0, reste));
    document.getElementById('sim-p-result').hidden = false;
  });
})();
</script>
