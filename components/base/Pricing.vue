<template>
    <div>
      <stripe-pricing-table pricing-table-id="prctbl_1Mdch6LaFe4PblPMwupFYn6c"
                            publishable-key="pk_live_51LnPXHLaFe4PblPMEmzabbWXHMGGkLBFh8IZDtU7kYVVHoZXFLiLnMovJrfUSI0oCw8VFCiiqvqBj4gv1bNvuus300CRH8xJnq">
      </stripe-pricing-table>
    </div>
  </template>
  
  <script>
  export default {
    head() {
      return {
        script: [
          {
            src: 'https://js.stripe.com/v3/pricing-table.js',
            async: true,
          },
        ],
      };
    },
  };
  </script>
  