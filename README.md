instagram-php-wrapper
=====================

Unofficial Instagram PHP Wrapper (v.0.1)

This wrapper class is compatible with the first version of the [Instagram API](http://instagram.com/developer)

This repository contains the PHP SDK that allows you to
access the Instagram platform from your PHP app.  


Usage
-----

The minimal you'll need to have is:

    require 'instagram-php-wrapper/src/instagram.php';

    $instagram = new Instagram(array(
      'clientId'  => 'YOUR_CLIENT_ID',
      'clientSecret' => 'YOUR_CLIENT_SECRET',
    ));

    // Get User ID
    $user = $instagram->api(
      "/users/{user-id}"
    );

To make API calls:

    // Set the Instagram access token to be used by the app
    $this->instagram->setAccessToken({access-token});

    // Return the recent media belonging to a specified Instagram user
    try {
      $media = $instagram->api(
        "/users/{$instagram->getUserId({access-token})}/media/recent"
      );
    } catch (InstagramApiException $e) {
      error_log($e);
      $media = null;
    }
