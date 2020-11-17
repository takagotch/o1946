###




```
<script src="https://js.stripe.com/v3/"></script>
var stripe = Stripe(
  'stripe PUBLIC KEY',
  {betas: ['payment_intent_beta_3']}
);
var elements = stripe.elements();

```

```payment.js
var stripeCard = elements.create('card');
stripeCard.mount('#creditCardHolder');

stripeCard.addEventListner('change', function(event) {
  var displayError = document.getElementById('card-errors');
  if (event.error) {
    displayError.textContent = event.error.message;
  } else {
    displayError.textContent = '';
  }
});

```

```
```

```
```

```
```

