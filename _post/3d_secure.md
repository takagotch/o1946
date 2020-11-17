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

// customer obj create
function createCustomer() {
  return $.ajax({
    type: "POST",
    url: "/customerCREATEURL",
  });
}

// paymentIntent obj CREATE
function createPaymentIntent(customerId) {
  return $.ajax({
    type: "POST",
    url: "/paymentIntentCREATEURL",
    data: {
      'totalCharge': $10000,
      'customer': customerId,
    }
  });
}

function provisionalPayment(clientSecret) {
  stripe.handleCardPayment(
    clientSecret,
    stripeCard,
    {
      source_data: {
        owner: {
          name: TAKASHI YOSHIOKA
        }
      },
    }
  ).then(function (result) {
    // SUCCESS
    // else 
    // ERR
  });
}
```

```payment.php
PaymentIntent::retrieve(paymentIntentId);
$paymentIntent->capture();
```
### https://qiita.com/yukidaru/items/c99185d89f7eb96921cf



```
```

```
```

