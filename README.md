# GETTING STARTED

You need a server running PHP:

- Unzip, and upload the files to a folder (i.e. /payment)
- Edit index.html, and replace your `Stripe Public key`

```js
var pk_live = "pk_live_1234567890";
```

- Edit the checkout.php and add your `Stripe Secret Key`

```php
\Stripe\Stripe::setApiKey('sk_live_1234567890');
```

- In the same checkout.php, update the domain, folder path, name and description:

```php
	$res = \Stripe\Checkout\Session::create([
	  'success_url' => 'https://www.domain.com/payment/success.html',
	  'cancel_url' => 'https://www.domain.com/payment/canceled.html',
	  'payment_method_types' => ['card'],
	  'line_items' => [
	    [
	      'name' => 'Payment',
	      'description' => 'Payment',
	      'amount' => $amount * 100,
	      'currency' => 'usd',
	      'quantity' => 1,
	    ],
	  ],
	]);
```

- Update index.html, cancelled.html, success.html and customize title tag and other strings, logo.
