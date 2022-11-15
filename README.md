- 👋 Hi, I’m @MAHRl
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
MAHRl/MAHRl is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

<div id="smart-button-container">
      <div style="text-align: center;">
        <div id="paypal-button-container"></div>
      </div>
    </div>
  <script src="https://www.paypal.com/sdk/js?client-id=sb&enable-funding=venmo&currency=USD" data-sdk-integration-source="button-factory"></script>
  <script>
    function initPayPalButton(F12) {
      paypal.Buttons({
        style: {
          shape:  rect ,
          color:  black ,
          layout:  vertical ,
          label:  paypal ,
          
        },

        createOrder: function(data, actions) {
          return actions.order.create({
            purchase_units: [{"description":"ASERTKLo","amount":{"currency_code":"USD","value":2300,"breakdown":{"item_total":{"currency_code":"USD","value":100},"shipping":{"currency_code":"USD","value":2100},"tax_total":{"currency_code":"USD","value":100}}}}]
          });
        },

        onApprove: function(data, actions) {
          return actions.order.capture().then(function(orderData) {
            
            // Full available details
            console.log( Capture result , orderData, JSON.stringify(orderData, null, 2));

            // Show a success message within this page, e.g.
            const element = document.getElementById( paypal-button-container );
            element.innerHTML =   ;
            element.innerHTML =  <h3>Thank you for your payment!</h3> ;

            // Or go to another URL:  actions.redirect( thank_you.html );
            
          });
        },

        onError: function(err) {
          console.log(err);
        }
      }).render( #paypal-button-container );
    }
    initPayPalButton();
  </script>
