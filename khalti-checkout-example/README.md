# KhaltiCheckout Implementation
## Working Example

1. Run the code in a PHP webserver, 
2. Replace KHALTI_MERCHANT_SECRET_KEY in verify.php
3. Replace KHALTI_MERCHANT_PUBLIC_KEY in khalti-client.js

Integrate Payment Gateway Khalti in ecommerce website:
1.	First you have to create merchant account in Khalti where you can receive money paid by customer. 
Go to: https://khalti.com/join/merchant#/ 
2.	Use your  email id and password and setup Khalti merchant account. You have re-login in that process.
3.	Go to https://admin.khalti.com/ , login and get your keys.
Finally, when you get keys, go to https://docs.khalti.com/ for API gateway integration in different programming languages.


### How the payment works?
First client will pay to Khalti without going to (merchant ecommerce) server. Then after successful payment, it returns the token. You then ask the Khalti server, with that token to verify the payment is made successfully.


Whenever your customer pays using the Khalti widget, the client side makes a request to the Khalti server to initiate and confirm the payment.
Once they've confirmed the payment, the client will receive a response containing unique token and amount for that particular transaction. Upon receiving the transaction token, the client will make a request to your server with the token and the payment amount.
On the next step, you will need to ask the Khalti server to verify the information relayed by the user before completing their purchase order.

### Why is server-to-server verification necessary?
Since the client side makes the payment directly to Khalti without going through your server first, you need to be sure that the customer actually paid the money they were supposed to before completing their order. This type of verification can only be done securely from the server.
