---
title: "Borrowing capacity calculator: free simulator 2026"
description: "Calculate your real estate borrowing capacity in 2 minutes. Free simulator based on the HCSF rule (35 % debt ratio), with deposit, co-borrower and duration."
translationKey: "sim-capacite"
layout: "simulator"
lastmod: 2026-04-30
faq:
  - question: "How is borrowing capacity calculated?"
    answer: "Borrowing capacity is the maximum capital a bank agrees to lend without exceeding the legal 35 percent debt ratio (HCSF rule). The bank takes the sum of net incomes, subtracts recurring charges, multiplies by 0.35 to get the maximum monthly payment, then converts that monthly payment into a capital amount based on the duration and rate of the loan."
  - question: "What salary to borrow 200,000 euros?"
    answer: "To borrow 200,000 euros over 20 years at 3.5 percent, with no charges and no deposit, you need a monthly payment of around 1,160 euros, that is a net monthly income of around 3,320 euros. With a 300 euro per month car loan, the required income rises to around 3,620 euros. Duration and deposit strongly modulate this threshold."
  - question: "What is the difference between borrowing capacity and purchasing capacity?"
    answer: "Borrowing capacity is the amount the bank agrees to lend. Purchasing capacity is the maximum price of the financeable property: borrowing capacity plus personal deposit, minus acquisition costs (notary fees, guarantee fees, file fees). The latter sets the ceiling of your real estate search."
  - question: "Which incomes are taken into account by the bank?"
    answer: "Banks count salaries on permanent contracts (CDI) outside the trial period at 100 percent, retirement pensions and stabilised rental income (often weighted at 70 to 80 percent). Variable bonuses, dividends and self-employed incomes are averaged over 2 to 3 years. Social benefits (CAF, RSA) are rarely included."
  - question: "How to increase your borrowing capacity?"
    answer: "Five levers: pay off a consumer loan to free up the debt ratio, increase the personal deposit (10 to 20 percent recommended), extend the loan duration up to 25 years, optimise the borrower insurance through external delegation, and mobilise a subsidised loan (PTZ, Action Logement, PAS) that does not weigh on the debt ratio."
---

How much can you borrow for your real estate project in France? The maximum amount depends on your income, your recurring charges and the legal 35 percent debt ceiling set by the HCSF since 2022. Our simulator estimates your borrowing capacity in seconds, with or without a co-borrower, taking into account your personal deposit and the target loan duration.

<div class="simulator-card">
<form id="sim-capacite" class="simulator-form">

  <div class="sim-field sim-field-full">
    <label>Household composition</label>
    <div class="sim-toggle" role="radiogroup" aria-label="Household composition">
      <input type="radio" name="composition" id="comp-seul" value="seul" checked>
      <label for="comp-seul">Solo</label>
      <input type="radio" name="composition" id="comp-deux" value="deux">
      <label for="comp-deux">Couple</label>
    </div>
  </div>

  <div class="sim-field">
    <label for="revenus">Monthly net income (€)</label>
    <input type="number" id="revenus" min="0" step="100" value="3500" required>
  </div>
  <div class="sim-field" id="field-revenus2" hidden>
    <label for="revenus2">Co-borrower monthly income (€)</label>
    <input type="number" id="revenus2" min="0" step="100" value="0">
  </div>

  <div class="sim-field">
    <label for="charges">Monthly charges (loans, alimony) (€)</label>
    <input type="number" id="charges" min="0" step="50" value="0">
  </div>
  <div class="sim-field">
    <label for="apport">Personal deposit (€)</label>
    <input type="number" id="apport" min="0" step="1000" value="0">
  </div>

  <div class="sim-field sim-field-full">
    <label>Loan duration</label>
    <div class="sim-toggle sim-toggle-duration" role="radiogroup" aria-label="Loan duration">
      <input type="radio" name="duree" id="d10" value="10">
      <label for="d10">10 years</label>
      <input type="radio" name="duree" id="d15" value="15">
      <label for="d15">15 years</label>
      <input type="radio" name="duree" id="d20" value="20" checked>
      <label for="d20">20 years</label>
      <input type="radio" name="duree" id="d25" value="25">
      <label for="d25">25 years</label>
    </div>
  </div>

  <div class="sim-field">
    <label for="taux">Annual interest rate (%)</label>
    <input type="number" id="taux" min="0" max="15" step="0.1" value="3.5" required>
  </div>

  <button type="submit" class="btn-primary">Calculate my capacity</button>
</form>

<div id="sim-result" class="simulator-result" hidden>
  <div class="sim-result-main">
    <span class="sim-result-label">Borrowing capacity</span>
    <span class="sim-result-value" id="result-montant">—</span>
  </div>
  <div class="sim-result-main sim-result-secondary">
    <span class="sim-result-label">Purchasing capacity (capital + deposit)</span>
    <span class="sim-result-value-small" id="result-achat">—</span>
  </div>
  <ul class="sim-result-details">
    <li>Maximum monthly payment: <strong id="result-mensualite">—</strong></li>
    <li>Total interest cost: <strong id="result-cout">—</strong></li>
    <li>Applied debt ratio: <strong>35 %</strong></li>
  </ul>
  <p class="sim-disclaimer">Indicative estimate. Only a bank can confirm your real capacity after a full case review.</p>
</div>
</div>

> **Key takeaways:**
> 1. Borrowing capacity is capped by the legal 35 percent debt ratio set by the HCSF.
> 2. A personal deposit of 10 to 20 percent is expected by most banks in 2026.
> 3. Extending the loan duration increases the borrowable capital but raises the total interest cost.
> 4. Paying off a consumer loan immediately frees up margin on the debt ratio.

## How your borrowing capacity is calculated

The calculation relies on the 35 percent maximum debt rule set by the High Council for Financial Stability (HCSF) since January 2022. The bank first deducts recurring charges from net income, applies the 35 percent rate to set the maximum monthly payment, then converts that payment into borrowable capital based on the loan duration and interest rate.

The formula:

1. Maximum monthly payment = (net income - charges) × 35 %
2. Borrowable capital = monthly payment × (1 - (1 + monthly rate)^(-months)) / monthly rate

### Which incomes are taken into account

- Salaries on permanent contracts (CDI) outside the trial period, counted at 100 percent.
- Retirement pensions and life annuities, counted at 100 percent.
- Stabilised rental income, weighted at 70 or 80 percent depending on the bank.
- Self-employed incomes, averaged over the last 2 or 3 fiscal years.
- Bonuses and variable pay, smoothed over the last 2 or 3 years.
- Social benefits (CAF, RSA) are not factored in by most banks.

### Which charges enter the calculation

- Monthly payments on existing loans (rental property, car, consumer credit).
- Alimony paid.
- Rents in case of dual residence.
- Existing rental charges are not counted if the purchase ends the rental.

## How much can you borrow based on your salary?

The table below gives an estimate of borrowing capacity for a single person, with no charges or deposit, at a 3.5 percent rate in 2026.

| Net monthly salary | 15 years | 20 years | 25 years |
|---|---|---|---|
| €1,500 | €73,400 | €90,500 | €104,900 |
| €2,000 | €97,900 | €120,700 | €139,800 |
| €2,500 | €122,400 | €150,900 | €174,800 |
| €3,000 | €146,900 | €181,000 | €209,700 |
| €3,500 | €171,400 | €211,200 | €244,700 |
| €4,000 | €195,800 | €241,400 | €279,700 |
| €5,000 | €244,800 | €301,700 | €349,600 |
| €6,000 | €293,800 | €362,100 | €419,500 |

These amounts assume a file with no recurring charges. Each €100 of existing loan repayment cuts about €17,000 of borrowable capital over 20 years.

## Two concrete calculation examples

> "Compliance with the 35 percent debt rule, insurance included, conditions 96 percent of accepted files in 2025."
> — High Council for Financial Stability, 2025 annual report

Example 1, couple with no existing loan.

- Combined net income: €4,000 per month.
- Charges: €0.
- Maximum monthly payment: 4,000 × 35 % = €1,400.
- Borrowing capacity over 20 years at 3.5 %: around €241,400.

Example 2, couple with an existing car loan.

- Combined net income: €4,000 per month.
- Charges: €300 car loan.
- Maximum monthly payment: (4,000 - 300) × 35 % = €1,295.
- Borrowing capacity over 20 years at 3.5 %: around €223,200.

The car loan costs around €18,000 of borrowing capacity, despite a monthly weight of just €300.

## Borrowing capacity vs purchasing capacity

The two notions are often confused but do not measure the same thing.

- Borrowing capacity is the capital the bank agrees to lend.
- Purchasing capacity is the maximum financeable property price. It adds the personal deposit to the borrowing capacity and subtracts acquisition costs (notary, guarantee, file fees).

For a couple with a borrowing capacity of €240,000 and a deposit of €30,000, the gross purchasing capacity is €270,000. After deducting around €22,000 of notary fees on the second-hand market and €2,000 of bank fees, the actual purchase budget falls around €246,000.

## The criteria that weigh on the bank's decision

Beyond the 35 percent rule, several qualitative criteria steer the bank's response.

- **Personal deposit**: 10 to 20 percent of the price recommended in 2026, to cover acquisition costs and reassure the bank.
- **Professional stability**: permanent contract outside trial period, civil servant, or self-employed with 3 positive financial years.
- **Remaining living budget**: the bank checks that at least €700 to €1,000 per adult remains after the monthly payment.
- **Age at end of loan**: most banks require repayment before age 75 or 80.
- **Charge jump**: a new file with a monthly payment more than 50 percent higher than the previous rent weakens the decision.
- **Banking history**: no recurring overdraft, no payment incident in the last 12 months.

## How to increase your borrowing capacity

Five levers are available before the loan application.

1. **Pay off a consumer loan**: each €100 of monthly payment freed up turns into around €17,000 of additional capacity over 20 years at 3.5 percent.
2. **Increase the personal deposit**: PEL savings, Livret A, family donations tax-exempt up to €100,000 per parent and per child every 15 years.
3. **Extend the loan duration**: moving from 20 to 25 years gains 16 to 17 percent of capacity but raises the total interest cost.
4. **Optimise borrower insurance**: external delegation can save up to 50 percent of insurance cost, freeing debt ratio.
5. **Mobilise a subsidised loan**: PTZ and Action Logement loans top up the main loan without weighing on the debt ratio.

## Subsidised loans to mobilise

Several public schemes top up the main loan without raising the debt burden.

- **Zero-rate loan (PTZ)**: from 1 April 2025 until 31 December 2027, accessible everywhere in France, finances up to 50 percent of the property depending on zone and household (€180,000 ceiling for new builds).
- **Action Logement loan**: up to €30,000 at 1 percent for private-sector employees.
- **Social Accession Loan (PAS)**: income-based, opens access to housing benefits and reduced fees.
- **Conventioned loan**: capped rate, no income condition, opens access to housing benefits.

To go further on financing, see our guides on [home loan financing strategies](/en/blog/home-loan-financing/) and [investing in real estate](/en/blog/how-to-invest-in-real-estate/). Before signing, also see our [buy or rent comparison](/en/blog/buy-or-rent-comparison/) and the [home buying checklist](/en/blog/buying-home-checklist/).

## Frequently asked questions

<details>
<summary>How is borrowing capacity calculated?</summary>

Borrowing capacity is the maximum capital a bank agrees to lend without exceeding the legal 35 percent debt ratio (HCSF rule). The bank takes the sum of net incomes, subtracts recurring charges, multiplies by 0.35 to get the maximum monthly payment, then converts that monthly payment into a capital amount based on the duration and rate of the loan.

</details>

<details>
<summary>What salary to borrow 200,000 euros?</summary>

To borrow 200,000 euros over 20 years at 3.5 percent, with no charges and no deposit, you need a monthly payment of around 1,160 euros, that is a net monthly income of around 3,320 euros. With a 300 euro per month car loan, the required income rises to around 3,620 euros. Duration and deposit strongly modulate this threshold.

</details>

<details>
<summary>What is the difference between borrowing capacity and purchasing capacity?</summary>

Borrowing capacity is the amount the bank agrees to lend. Purchasing capacity is the maximum price of the financeable property: borrowing capacity plus personal deposit, minus acquisition costs (notary fees, guarantee fees, file fees). The latter sets the ceiling of your real estate search.

</details>

<details>
<summary>Which incomes are taken into account by the bank?</summary>

Banks count salaries on permanent contracts (CDI) outside the trial period at 100 percent, retirement pensions and stabilised rental income (often weighted at 70 to 80 percent). Variable bonuses, dividends and self-employed incomes are averaged over 2 to 3 years. Social benefits (CAF, RSA) are rarely included.

</details>

<details>
<summary>How to increase your borrowing capacity?</summary>

Five levers: pay off a consumer loan to free up the debt ratio, increase the personal deposit (10 to 20 percent recommended), extend the loan duration up to 25 years, optimise the borrower insurance through external delegation, and mobilise a subsidised loan (PTZ, Action Logement, PAS) that does not weigh on the debt ratio.

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

    var fmt = new Intl.NumberFormat('en-GB', { style: 'currency', currency: 'EUR', maximumFractionDigits: 0 });
    document.getElementById('result-montant').textContent = fmt.format(capital);
    document.getElementById('result-achat').textContent = fmt.format(capaciteAchat);
    document.getElementById('result-mensualite').textContent = fmt.format(mensualite);
    document.getElementById('result-cout').textContent = fmt.format(Math.max(0, cout));
    document.getElementById('sim-result').hidden = false;
  });
})();
</script>
