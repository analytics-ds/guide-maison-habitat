---
title: "Simulateur de capacité d'emprunt"
description: "Calculez votre capacité d'emprunt immobilier en fonction de vos revenus, charges, durée et taux d'intérêt. Gratuit et instantané."
translationKey: "sim-capacite"
layout: "simulator"
---

Le **simulateur de capacité d'emprunt** estime le montant maximal que vous pouvez emprunter pour un achat immobilier, en respectant la limite légale de 35 pour cent de taux d'endettement fixée par le HCSF.

<div class="simulator-card">
<form id="sim-capacite" class="simulator-form">
  <div class="sim-field">
    <label for="revenus">Revenus nets mensuels du foyer (€)</label>
    <input type="number" id="revenus" min="0" step="100" value="3500" required>
  </div>
  <div class="sim-field">
    <label for="charges">Charges mensuelles (crédits, pensions) (€)</label>
    <input type="number" id="charges" min="0" step="50" value="0">
  </div>
  <div class="sim-field">
    <label for="duree">Durée du prêt (années)</label>
    <input type="number" id="duree" min="5" max="25" step="1" value="20" required>
  </div>
  <div class="sim-field">
    <label for="taux">Taux d'intérêt annuel (%)</label>
    <input type="number" id="taux" min="0" max="15" step="0.1" value="3.5" required>
  </div>
  <button type="submit" class="btn-primary">Calculer</button>
</form>

<div id="sim-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Capacité d'emprunt estimée</span>
    <span class="sim-result-value" id="result-montant">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Mensualité maximale : <strong id="result-mensualite">—</strong></li>
    <li>Coût total du crédit : <strong id="result-cout">—</strong></li>
    <li>Taux d'endettement appliqué : <strong>35 %</strong></li>
  </ul>
  <p class="sim-disclaimer">Estimation indicative. Seule une banque peut confirmer votre capacité d'emprunt réelle.</p>
</div>
</div>

## Comment fonctionne le calcul

La capacité d'emprunt est déterminée par le taux d'endettement maximal légal de 35 pour cent des revenus nets (règle du HCSF depuis 2022).

La formule utilisée :

1. **Mensualité maximale** = (Revenus - Charges) × 35 %
2. **Capital empruntable** = Mensualité × (1 - (1 + taux/12)^(-mois)) / (taux/12)

## Les 3 critères qui font la différence

- **Apport personnel** : un apport de 10 à 20 pour cent améliore sensiblement votre taux
- **Stabilité professionnelle** : CDI hors période d'essai exigé par la majorité des banques
- **Reste à vivre** : au-delà du taux d'endettement, la banque vérifie qu'il reste au moins 700 à 1000 euros par personne au foyer

Pour approfondir, consultez notre [guide financement crédit immobilier](/blog/financement-credit-immobilier/) qui détaille les stratégies pour obtenir le meilleur taux.

<script>
(function() {
  var form = document.getElementById('sim-capacite');
  if (!form) return;
  form.addEventListener('submit', function(e) {
    e.preventDefault();
    var revenus = parseFloat(document.getElementById('revenus').value) || 0;
    var charges = parseFloat(document.getElementById('charges').value) || 0;
    var duree = parseInt(document.getElementById('duree').value, 10) || 20;
    var taux = parseFloat(document.getElementById('taux').value) || 0;
    var mensualite = Math.max(0, (revenus - charges) * 0.35);
    var mois = duree * 12;
    var tauxM = taux / 100 / 12;
    var capital = tauxM > 0 ? mensualite * (1 - Math.pow(1 + tauxM, -mois)) / tauxM : mensualite * mois;
    var cout = mensualite * mois - capital;
    var fmt = new Intl.NumberFormat('fr-FR', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
    document.getElementById('result-montant').textContent = fmt.format(capital);
    document.getElementById('result-mensualite').textContent = fmt.format(mensualite);
    document.getElementById('result-cout').textContent = fmt.format(Math.max(0, cout));
    document.getElementById('sim-result').hidden = false;
  });
})();
</script>
