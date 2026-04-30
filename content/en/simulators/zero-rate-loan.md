---
title: "Zero-rate loan calculator (PTZ): free simulator 2026"
description: "Calculate your French zero-rate loan (PTZ) 2026 by zone, income, household size and property type. 2025-2027 reform integrated, official ceilings up to date."
translationKey: "sim-ptz"
layout: "simulator"
lastmod: 2026-04-30
faq:
  - question: "Who can benefit from the French zero-rate loan in 2026?"
    answer: "The PTZ is reserved for first-time buyers, that is households who have not been owners of their main home in the last 2 years. Three exceptions: disability status, disaster making the home permanently uninhabitable, and holders of the Mobility Inclusion Card. The purchased property must become the main residence within one year of acquisition."
  - question: "Which properties are eligible after the 1 April 2025 reform?"
    answer: "Since 1 April 2025 and until 31 December 2027, the PTZ is accessible everywhere in France for new collective housing (apartments) and new individual housing (houses) under energy performance conditions, as well as for old properties with at least 25 percent of renovation works in zones B2 and C, and for old social housing."
  - question: "What are the PTZ income ceilings in 2026?"
    answer: "The 2025-2026 ceilings depend on the zone and the number of people in the household. In zone A and A bis, they range from €49,000 for one person to €161,700 from 8 people. In zones B2 and C, they range from €31,500 to €103,950. The bank uses the N-2 reference fiscal income or the total operation cost divided by 9 if higher."
  - question: "How is the PTZ amount calculated?"
    answer: "The amount is the property price (capped by zone and household size) multiplied by a percentage that depends on your income tier (T1 to T4) and the property type. The percentage ranges from 10 to 50 percent. In new collective housing, the most modest households can obtain up to 50 percent of their project as a PTZ, within the operation ceilings."
  - question: "How is the PTZ repaid?"
    answer: "The PTZ is repaid in 2 periods after a deferral phase where no monthly payment is due. The deferral lasts 5, 10 or 15 years depending on the income tier, then repayment runs over an additional 10 to 15 years. Total duration is 20 to 25 years depending on the profile. The most modest households benefit from the longest deferral."
---

The PTZ (Prêt à Taux Zéro) is an interest-free loan granted by the French State to first-time buyers to finance part of their main residence. Since 1 April 2025, it is accessible everywhere in France and until 31 December 2027, with eligibility extended to new houses. Our simulator estimates your PTZ in seconds, integrating income ceilings, operation ceilings and the official 2025-2026 percentages.

<div class="simulator-card">
<form id="sim-ptz" class="simulator-form">

  <div class="sim-field sim-field-full">
    <label>Have you been an owner of your main residence in the last 2 years?</label>
    <div class="sim-toggle" role="radiogroup" aria-label="First-time buyer status">
      <input type="radio" name="proprio" id="prop-non" value="non" checked>
      <label for="prop-non">No</label>
      <input type="radio" name="proprio" id="prop-oui" value="oui">
      <label for="prop-oui">Yes</label>
    </div>
  </div>

  <div class="sim-field">
    <label for="p-revenu">N-2 reference fiscal income (€/year)</label>
    <input type="number" id="p-revenu" min="0" step="500" value="40000" required>
  </div>
  <div class="sim-field">
    <label for="p-personnes">Number of people in household</label>
    <input type="number" id="p-personnes" min="1" max="8" step="1" value="2" required>
  </div>

  <div class="sim-field">
    <label for="p-zone">Geographical zone</label>
    <select id="p-zone" required>
      <option value="A">Zone A bis / A (Paris and tense large cities)</option>
      <option value="B1" selected>Zone B1 (250,000+ inhabitant areas)</option>
      <option value="B2">Zone B2 (mid-sized cities)</option>
      <option value="C">Zone C (relaxed areas)</option>
    </select>
  </div>
  <div class="sim-field">
    <label for="p-type">Property type</label>
    <select id="p-type" required>
      <option value="neuf_collectif">New collective (apartment)</option>
      <option value="neuf_individuel">New individual (house)</option>
      <option value="ancien">Old with 25 % works (B2 and C)</option>
      <option value="hlm_ancien">Old social housing</option>
    </select>
  </div>

  <div class="sim-field">
    <label for="p-prix">Property price (€)</label>
    <input type="number" id="p-prix" min="0" step="1000" value="250000" required>
  </div>
  <div class="sim-field">
    <label for="p-apport">Personal deposit (€)</label>
    <input type="number" id="p-apport" min="0" step="1000" value="0">
  </div>

  <button type="submit" class="btn-primary">Calculate my PTZ</button>
</form>

<div id="sim-p-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Estimated PTZ amount</span>
    <span class="sim-result-value" id="p-result-montant">—</span>
  </div>
  <div class="sim-result-main sim-result-secondary">
    <span class="sim-result-label">Remaining to finance (excluding deposit and fees)</span>
    <span class="sim-result-value-small" id="p-result-reste">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Income tier: <strong id="p-result-tranche">—</strong></li>
    <li>Operation ceiling applied: <strong id="p-result-plafond">—</strong></li>
    <li>PTZ percentage applied: <strong id="p-result-quotite">—</strong></li>
    <li>Estimated total duration: <strong id="p-result-duree">—</strong></li>
    <li>Deferral period: <strong id="p-result-differe">—</strong></li>
  </ul>
  <p class="sim-disclaimer">Indicative estimate based on the official 2025-2026 scale. The PTZ is subject to specific conditions to be confirmed with a State-conventioned bank.</p>
</div>

<div id="sim-p-non-eligible" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">PTZ eligibility</span>
    <span class="sim-result-value" style="color:#a14a4a">Not eligible</span>
  </div>
  <p id="p-result-raison" class="sim-disclaimer"></p>
  <p class="sim-disclaimer">This estimate uses standard rules. Exceptions exist (disability, disaster, mobility inclusion). Check your situation with a conventioned bank.</p>
</div>
</div>

> **Key takeaways:**
> 1. The PTZ is an interest-free loan reserved for first-time buyers of a main residence in France.
> 2. Since 1 April 2025, it is accessible everywhere in France for new collective and new individual housing.
> 3. The amount depends on the zone, household size, property type and income tier (T1 to T4).
> 4. Repayment starts after a deferral period of 5, 10 or 15 years, over a total duration of 20 to 25 years.

## What is the French zero-rate loan?

The PTZ (Prêt à Taux Zéro) is a State-subsidised loan, granted without interest or file fees. Created in 1995 to support home ownership, it targets households with intermediate or modest incomes who buy their first main residence. It never finances the entire project: it complements a classic home loan and a possible personal deposit.

The PTZ is distributed only by banks conventioned by the French State. The financed property must become the main residence within one year of acquisition, and remain so for at least 6 years (with some exceptions).

## PTZ 2026: the 1 April 2025 reform

The 2025 finance act deeply reshaped the PTZ with a reform effective from 1 April 2025 and applicable until 31 December 2027. Four major changes.

- The PTZ is now accessible everywhere in France for new collective (apartment) and new individual (house) housing, whereas new houses were previously restricted to zones B2 and C.
- The maximum percentage rises to 50 percent of the property price for the most modest households in new collective housing.
- Operation ceilings are updated (up to €360,000 in zone A for 5 people or more).
- Energy performance conditions for new housing are reinforced (RE2020).

## Who can benefit from the PTZ?

Eligibility relies on two main conditions: first-time buyer status and compliance with income ceilings.

### First-time buyers

The PTZ is reserved for households who have not been owners of their main residence in the 2 years preceding the loan offer. Owning a second home or a rental investment does not prevent eligibility.

### Exceptions

Three situations allow access to the PTZ even when one has been an owner recently.

- Holder of a Mobility Inclusion Card with "disability" mention.
- Beneficiary of the disabled adult allowance or the disabled child education allowance.
- Disaster having rendered the home permanently uninhabitable (natural or technological catastrophe).

## Which properties are eligible for the PTZ?

Four categories of properties open the right to the PTZ since the 2025 reform.

### New collective housing

Any new apartment, off-plan or under construction, is eligible everywhere in France, in all zones (A, A bis, B1, B2, C). This is the main segment covered by the 2025 reform.

### New individual housing

New individual houses are now eligible everywhere, subject to compliance with the RE2020 standard. Before the reform, they were eligible only in zones B2 and C with a reduced percentage.

### Old housing with 25 % works

An old eligible property must be renovated with works representing at least 25 percent of the total operation cost. This route is reserved for zones B2 and C, with a mandatory energy gain after works.

### Old social housing

The purchase of a social housing unit (HLM) by its tenant opens the right to the PTZ, at a reduced rate (10 percent of the price). This is a specific route to encourage social home ownership.

## PTZ 2026 income ceilings

The household's N-2 reference fiscal income must not exceed the following thresholds. Otherwise, the total operation cost divided by 9 is used for comparison if this amount is higher.

| People | Zone A and A bis | Zone B1 | Zones B2 and C |
|---|---|---|---|
| 1 | €49,000 | €34,500 | €31,500 |
| 2 | €73,500 | €51,750 | €47,250 |
| 3 | €88,200 | €62,100 | €56,700 |
| 4 | €102,900 | €72,450 | €66,150 |
| 5 | €117,600 | €82,800 | €75,600 |
| 6 | €132,300 | €93,150 | €85,050 |
| 7 | €147,000 | €103,500 | €94,500 |
| 8+ | €161,700 | €113,850 | €103,950 |

## PTZ 2026 operation ceilings

The PTZ does not apply to the full property price, but within an operation ceiling that depends on the zone and the household size.

| People | Zone A and A bis | Zone B1 | Zone B2 | Zone C |
|---|---|---|---|---|
| 1 | €150,000 | €135,000 | €110,000 | €100,000 |
| 2 | €225,000 | €202,500 | €165,000 | €150,000 |
| 3 | €270,000 | €243,000 | €198,000 | €180,000 |
| 4 | €315,000 | €283,500 | €231,000 | €210,000 |
| 5+ | €360,000 | €324,000 | €264,000 | €240,000 |

## How is the PTZ amount calculated?

The PTZ amount is obtained in two steps.

1. The calculation base is the minimum of the property price and the operation ceiling applicable based on the zone and household size.
2. A percentage is applied to that base, depending on the household's income tier (T1 to T4) and property type.

After the 2025 reform, percentages reach 50 percent of the ceiling for households in T1 and T2 in new collective housing, which can represent up to €180,000 of PTZ for a modest household in zone A. For wealthier households (T4), the percentage drops to 10 or 20 percent depending on the property type.

> "Extending the PTZ to new houses in all zones is the most structuring change for first-time buyers since 2018."
> — French Ministry of Housing, March 2025 press release

To calibrate your purchase project, simulate first your [borrowing capacity](/en/simulators/borrowing-capacity/) and then your loan repayments on the main loan that will complement the PTZ.

## How is the PTZ repaid?

Repayment runs over 2 successive periods, after a total deferral phase where no monthly payment is due.

- Deferral period: 5, 10 or 15 years depending on income tier (T4 to T1). During this phase, only the main loan is repaid.
- Period 1: capital repayment without interest, over 10 to 15 years.
- Total duration (deferral + repayment) ranges from 20 years for T4 profiles to 25 years for T1 profiles.

This two-step structure lightens cumulative monthly payments at the start of the project, when the borrower also bears acquisition fees and property fitting costs.

## How to obtain the PTZ?

The PTZ can only be subscribed with a State-conventioned bank. Most major French banks (Crédit Agricole, BNP Paribas, Société Générale, Banque Populaire, Caisse d'Épargne, LCL, Crédit Mutuel, Hello bank, CCF) are conventioned.

The PTZ is always backed by a main loan: there is no 100 percent PTZ home financing. It can be combined with the Action Logement loan, the Social Accession Loan (PAS), a savings home loan (PEL/CEL) and a classic loan.

To go further on financing, see our guides on [home loan financing strategies](/en/blog/home-loan-financing/) and [investing in real estate](/en/blog/how-to-invest-in-real-estate/). Before signing, also see our [home buying checklist](/en/blog/buying-home-checklist/) and our [buy or rent comparison](/en/blog/buy-or-rent-comparison/).

## Frequently asked questions

<details>
<summary>Who can benefit from the French zero-rate loan in 2026?</summary>

The PTZ is reserved for first-time buyers, that is households who have not been owners of their main home in the last 2 years. Three exceptions: disability status, disaster making the home permanently uninhabitable, and holders of the Mobility Inclusion Card. The purchased property must become the main residence within one year of acquisition.

</details>

<details>
<summary>Which properties are eligible after the 1 April 2025 reform?</summary>

Since 1 April 2025 and until 31 December 2027, the PTZ is accessible everywhere in France for new collective housing (apartments) and new individual housing (houses) under energy performance conditions, as well as for old properties with at least 25 percent of renovation works in zones B2 and C, and for old social housing.

</details>

<details>
<summary>What are the PTZ income ceilings in 2026?</summary>

The 2025-2026 ceilings depend on the zone and the number of people in the household. In zone A and A bis, they range from €49,000 for one person to €161,700 from 8 people. In zones B2 and C, they range from €31,500 to €103,950. The bank uses the N-2 reference fiscal income or the total operation cost divided by 9 if higher.

</details>

<details>
<summary>How is the PTZ amount calculated?</summary>

The amount is the property price (capped by zone and household size) multiplied by a percentage that depends on your income tier (T1 to T4) and the property type. The percentage ranges from 10 to 50 percent. In new collective housing, the most modest households can obtain up to 50 percent of their project as a PTZ, within the operation ceilings.

</details>

<details>
<summary>How is the PTZ repaid?</summary>

The PTZ is repaid in 2 periods after a deferral phase where no monthly payment is due. The deferral lasts 5, 10 or 15 years depending on the income tier, then repayment runs over an additional 10 to 15 years. Total duration is 20 to 25 years depending on the profile. The most modest households benefit from the longest deferral.

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

  var fmt = new Intl.NumberFormat('en-GB', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
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
      showNonEligible('You have been an owner of your main residence in the last 2 years. The PTZ is reserved for first-time buyers, except for specific cases (disability, disaster).');
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
      showNonEligible('Your income (' + fmt.format(revenu) + ') exceeds the PTZ ceiling for your zone and household composition (' + fmt.format(plafondR) + ').');
      return;
    }

    if ((type === 'ancien' || type === 'hlm_ancien') && (zone === 'A' || zone === 'B1')) {
      showNonEligible('The PTZ for old housing with works or for old social housing is reserved for zones B2 and C.');
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
    document.getElementById('p-result-duree').textContent = modalite.duree + ' years';
    document.getElementById('p-result-differe').textContent = modalite.differe + ' years';
    resultNon.hidden = true;
    resultEligible.hidden = false;
  });
})();
</script>
