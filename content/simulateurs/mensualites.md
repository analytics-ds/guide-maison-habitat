---
title: "Simulateur de mensualités de prêt immobilier"
description: "Calculez les mensualités de votre prêt immobilier selon le montant emprunté, le taux et la durée. Coût total du crédit inclus."
translationKey: "sim-mensualites"
layout: "simulator"
---

Le **simulateur de mensualités** calcule instantanément le montant à rembourser chaque mois pour un prêt immobilier donné, ainsi que le coût total du crédit sur toute la durée.

<div class="simulator-card">
<form id="sim-mensualites" class="simulator-form">
  <div class="sim-field">
    <label for="m-montant">Montant emprunté (€)</label>
    <input type="number" id="m-montant" min="0" step="1000" value="200000" required>
  </div>
  <div class="sim-field">
    <label for="m-duree">Durée du prêt (années)</label>
    <input type="number" id="m-duree" min="5" max="25" step="1" value="20" required>
  </div>
  <div class="sim-field">
    <label for="m-taux">Taux d'intérêt annuel (%)</label>
    <input type="number" id="m-taux" min="0" max="15" step="0.1" value="3.5" required>
  </div>
  <div class="sim-field">
    <label for="m-assurance">Taux assurance emprunteur annuel (%)</label>
    <input type="number" id="m-assurance" min="0" max="2" step="0.05" value="0.3">
  </div>
  <button type="submit" class="btn-primary">Calculer</button>
</form>

<div id="sim-m-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Mensualité totale (crédit + assurance)</span>
    <span class="sim-result-value" id="m-result-mensualite">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Mensualité hors assurance : <strong id="m-result-hors">—</strong></li>
    <li>Coût de l'assurance : <strong id="m-result-assurance">—</strong></li>
    <li>Intérêts totaux : <strong id="m-result-interets">—</strong></li>
    <li>Coût total du crédit : <strong id="m-result-cout">—</strong></li>
  </ul>
  <p class="sim-disclaimer">Estimation indicative. Hors frais de dossier et garantie.</p>
</div>
</div>

## La formule de calcul

La mensualité d'un crédit à taux fixe se calcule avec la formule :

**Mensualité = Capital × (t/12) / (1 - (1 + t/12)^(-n))**

Où : t = taux annuel, n = nombre total de mois.

## L'impact de chaque variable

- **Durée** : chaque année supplémentaire réduit la mensualité d'environ 5 à 7 pour cent, mais alourdit le coût total
- **Taux** : 1 point d'écart sur le taux représente environ 15 000 euros sur 200 000 empruntés sur 20 ans
- **Assurance** : la délégation d'assurance peut diviser son coût par 2 ou 3

Pour optimiser votre prêt, consultez notre [guide financement crédit immobilier](/blog/financement-credit-immobilier/) et notre [guide assurance emprunteur](/blog/assurance-emprunteur-guide/).

<script>
(function() {
  var form = document.getElementById('sim-mensualites');
  if (!form) return;
  form.addEventListener('submit', function(e) {
    e.preventDefault();
    var capital = parseFloat(document.getElementById('m-montant').value) || 0;
    var duree = parseInt(document.getElementById('m-duree').value, 10) || 20;
    var taux = parseFloat(document.getElementById('m-taux').value) || 0;
    var assu = parseFloat(document.getElementById('m-assurance').value) || 0;
    var mois = duree * 12;
    var tauxM = taux / 100 / 12;
    var mensHors = tauxM > 0 ? capital * tauxM / (1 - Math.pow(1 + tauxM, -mois)) : capital / mois;
    var mensAssu = capital * (assu / 100) / 12;
    var mensTotale = mensHors + mensAssu;
    var interets = mensHors * mois - capital;
    var coutAssu = mensAssu * mois;
    var coutTotal = interets + coutAssu;
    var fmt = new Intl.NumberFormat('fr-FR', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
    document.getElementById('m-result-mensualite').textContent = fmt.format(mensTotale);
    document.getElementById('m-result-hors').textContent = fmt.format(mensHors);
    document.getElementById('m-result-assurance').textContent = fmt.format(mensAssu) + ' / mois';
    document.getElementById('m-result-interets').textContent = fmt.format(Math.max(0, interets));
    document.getElementById('m-result-cout').textContent = fmt.format(Math.max(0, coutTotal));
    document.getElementById('sim-m-result').hidden = false;
  });
})();
</script>
