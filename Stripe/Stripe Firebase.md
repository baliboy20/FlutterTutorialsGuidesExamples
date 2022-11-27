
# Deploying main.js to Firebase functions

__1. npm run deploy__

__2. set environment variable for the Pkey__
   for this code line looking for an env value pktest: -

    
    const stripe = require('stripe')(functions.config().pktest);

 set the following value form the terminal command line. should pick it up from the env file but
it doesn't.
   
      ` stripe config --set PKTEST pk_test_gESpLAexm8oTAFcLjCNEQkOw00smIXKrfx`

