---
layout: schedule
title: CSSE
units: "1,2,3,4,5,6"
course: csse
---



<script type="module">
    // uri variable and options object are obtained from config.js
    import { uri, options } from '{{site.baseurl}}/assets/js/api/config.js';

    function login_user(){
        // Set Authenticate endpoint
        const url = uri + '/api/users/authenticate';

        // Set the body of the request to include login data from the DOM
        const body = {
            uid: document.getElementById("uid").value,
            password: document.getElementById("password").value,
        };

        // Change options according to Authentication requirements
        const authOptions = {
            ...options, // This will copy all properties from options
            method: 'POST', // Override the method property
            cache: 'no-cache', // Set the cache property
            body: JSON.stringify(body)
        };

        // Fetch JWT
        fetch(url, authOptions)
        .then(response => {
            // handle error response from Web API
            if (!response.ok) {
                const errorMsg = 'Login error: ' + response.status;
                console.log(errorMsg);
                return;
            }
            // Success!!!
            // Redirect to the database page
            window.location.href = "{{site.baseurl}}/data/database";
        })
        // catch fetch errors (ie ACCESS to server blocked)
        .catch(err => {
            console.error(err);
        });
    }

    window.login_user = login_user;
</script>