<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Calculate your estimated monthly mortgage repayments and total repayment.">
  <title>Mortgage Repayment Calculator</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@500;700&display=swap" rel="stylesheet">

  <link rel="stylesheet" href="style.css">
  <script src="script.js" defer></script>
</head>

<body>
  <main class="calculator">
    <section class="form-panel" aria-labelledby="page-title">
      <div class="heading-row">
        <h1 id="page-title">Mortgage Calculator</h1>
        <button class="clear-button" id="clear-button" type="button">
          Clear All
        </button>
      </div>

      <form id="mortgage-form" novalidate>
        <div class="field-group">
          <label for="mortgage-amount">Mortgage Amount</label>

          <div class="input-wrap" id="amount-wrap">
            <span class="input-prefix" aria-hidden="true">£</span>
            <input
              id="mortgage-amount"
              name="mortgageAmount"
              type="text"
              inputmode="decimal"
              aria-describedby="amount-error"
            >
          </div>

          <p class="error-message" id="amount-error"></p>
        </div>

        <div class="two-columns">
          <div class="field-group">
            <label for="mortgage-term">Mortgage Term</label>

            <div class="input-wrap suffix-wrap" id="term-wrap">
              <input
                id="mortgage-term"
                name="mortgageTerm"
                type="number"
                min="1"
                step="1"
                aria-describedby="term-error"
              >
              <span class="input-suffix" aria-hidden="true">years</span>
            </div>

            <p class="error-message" id="term-error"></p>
          </div>

          <div class="field-group">
            <label for="interest-rate">Interest Rate</label>

            <div class="input-wrap suffix-wrap" id="rate-wrap">
              <input
                id="interest-rate"
                name="interestRate"
                type="number"
                min="0"
                step="any"
                aria-describedby="rate-error"
              >
              <span class="input-suffix" aria-hidden="true">%</span>
            </div>

            <p class="error-message" id="rate-error"></p>
          </div>
        </div>

        <fieldset class="field-group mortgage-type">
          <legend>Mortgage Type</legend>

          <label class="radio-option" for="repayment">
            <input
              id="repayment"
              type="radio"
              name="mortgageType"
              value="repayment"
              checked
            >
            <span class="custom-radio" aria-hidden="true"></span>
            <span>Repayment</span>
          </label>

          <label class="radio-option" for="interest-only">
            <input
              id="interest-only"
              type="radio"
              name="mortgageType"
              value="interest-only"
            >
            <span class="custom-radio" aria-hidden="true"></span>
            <span>Interest Only</span>
          </label>
        </fieldset>

        <button class="calculate-button" type="submit">
          <span aria-hidden="true">✣</span>
          Calculate Repayments
        </button>
      </form>
    </section>

    <section class="results-panel" aria-labelledby="results-title">

      <div class="empty-state" id="empty-state">
        <div class="calculator-icon" aria-hidden="true">▦</div>

        <h2 id="results-title">Results shown here</h2>

        <p>
          Complete the form and click “calculate repayments”
          to see what your monthly repayments would be.
        </p>
      </div>

      <div
        class="calculated-results"
        id="calculated-results"
        hidden
        aria-live="polite"
      >
        <h2>Your results</h2>

        <p class="results-intro">
          Your results are shown below based on the information
          you provided. To adjust the results, edit the form and
          click “calculate repayments” again.
        </p>

        <div class="result-card">
          <p class="result-label">Your monthly repayments</p>

          <p class="monthly-value" id="monthly-result">
            £0.00
          </p>

          <div class="result-divider"></div>

          <p class="result-label">
            Total you'll repay over the term
          </p>

          <p class="total-value" id="total-result">
            £0.00
          </p>
        </div>
      </div>

    </section>
  </main>
</body>
</html>
