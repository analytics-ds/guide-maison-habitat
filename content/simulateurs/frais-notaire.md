---
title: "Simulateur de frais de notaire"
description: "Calculez les frais de notaire pour l'achat d'un bien immobilier neuf ou ancien. Estimation instantanée."
translationKey: "sim-notaire"
layout: "simulator"
---

Le **simulateur de frais de notaire** estime le montant des frais d'acquisition à prévoir lors d'un achat immobilier, selon que le bien est neuf ou ancien.

<div class="simulator-card">
<form id="sim-notaire" class="simulator-form">
  <div class="sim-field">
    <label for="n-prix">Prix du bien (€)</label>
    <input type="number" id="n-prix" min="0" step="1000" value="250000" required>
  </div>
  <div class="sim-field">
    <label for="n-type">Type de bien</label>
    <select id="n-type" required>
      <option value="ancien">Ancien (plus de 5 ans)</option>
      <option value="neuf">Neuf (moins de 5 ans ou VEFA)</option>
    </select>
  </div>
  <button type="submit" class="btn-primary">Calculer</button>
</form>

<div id="sim-n-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Frais de notaire estimés</span>
    <span class="sim-result-value" id="n-result-frais">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Taux appliqué : <strong id="n-result-taux">—</strong></li>
    <li>Coût total (prix + frais) : <strong id="n-result-total">—</strong></li>
    <li>Détail : droits de mutation, émoluments et débours</li>
  </ul>
  <p class="sim-disclaimer">Estimation indicative. Les frais réels dépendent du département et du type précis de bien.</p>
</div>
</div>

## Composition des frais de notaire

Les frais de notaire ne reviennent pas au notaire. Ils se décomposent ainsi :

- **Droits de mutation** (80 %) : taxes perçues par l'État et le département
- **Émoluments du notaire** (10 %) : rémunération réglementée
- **Débours** (5 %) : frais avancés par le notaire pour vous (géomètre, cadastre)
- **TVA et divers** (5 %)

## Les taux 2026

| Type de bien | Frais de notaire |
|--------------|------------------|
| Ancien (plus de 5 ans) | 7 à 8 % du prix |
| Neuf (VEFA ou moins de 5 ans) | 2 à 3 % du prix |
| Terrain à bâtir | 7 à 8 % du prix |

## Les astuces pour réduire les frais

- Déduire la valeur du mobilier du prix (jusqu'à 5 % du bien)
- Vérifier le calcul (erreur fréquente sur les émoluments)
- Préférer le neuf si le budget le permet (frais divisés par 3)

Pour sécuriser votre achat, suivez notre [checklist achat maison](/blog/achat-maison-checklist/) et arbitrez avec notre [comparatif acheter ou louer](/blog/acheter-ou-louer-comparatif/).

<script>
(function() {
  var form = document.getElementById('sim-notaire');
  if (!form) return;
  form.addEventListener('submit', function(e) {
    e.preventDefault();
    var prix = parseFloat(document.getElementById('n-prix').value) || 0;
    var type = document.getElementById('n-type').value;
    var taux = type === 'neuf' ? 0.025 : 0.075;
    var frais = prix * taux;
    var fmt = new Intl.NumberFormat('fr-FR', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
    document.getElementById('n-result-frais').textContent = fmt.format(frais);
    document.getElementById('n-result-taux').textContent = (taux * 100).toFixed(1) + ' %';
    document.getElementById('n-result-total').textContent = fmt.format(prix + frais);
    document.getElementById('sim-n-result').hidden = false;
  });
})();
</script>
