<template>
    <div>
      <!-- Messenger Chat Plugin Code -->
      <div id="fb-root"></div>
      <div id="fb-customer-chat" class="fb-customerchat"></div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'FacebookChat',
    mounted() {
      this.loadFacebookSDK();
    },
    methods: {
      loadFacebookSDK() {
        var chatbox = document.getElementById('fb-customer-chat');
        chatbox.setAttribute("page_id", "434892216844025");
        chatbox.setAttribute("attribution", "biz_inbox");

        window.fbAsyncInit = function() {
          FB.init({
            xfbml: true,
            version: 'v14.0'
          });
        };
  
        (function(d, s, id) {
          var js, fjs = d.getElementsByTagName(s)[0];
          if (d.getElementById(id)) return;
          js = d.createElement(s); js.id = id;
          js.src = 'https://connect.facebook.net/en_US/sdk/xfbml.customerchat.js';
          fjs.parentNode.insertBefore(js, fjs);
        }(document, 'script', 'facebook-jssdk'));
      }
    }
  }
  </script>