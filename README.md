# WSOAuth

## YDMS Fork Notes

### Resonite Provider
YDMS forked this to add our own provider, You can find it in: `src/AuthenticationProvider/ResoniteAuth.php`.

Based on the [documentation for adding providers](https://www.mediawiki.org/wiki/Extension:WSOAuth/For_developers#Adding_a_new_OAuth_provider_to_WSOAuth), maintaining a fork for your own provider might not be the best way to achieve a custom provider.

Something like:

```php
$wgOAuthCustomAuthProviders = [
    'google' => ResoniteAuth\ResoniteAuth::class 
];
```

Could be used instead to keep our AuthProvider separate, and in a separate repo.

There's an example of doing this [here](https://github.com/Kneemund/mediawiki-discord-oauth). That repo is quite out of date though, so for initial implementation we went for a fork. We aim to review this eventually, but if you're here in a few years reading this then... sorry I guess :). Open an issue if you wish to discuss.

### User Info Saving

We also made [really small edits](https://github.com/Yellow-Dog-Man/mediawiki-extensions-WSOAuth/commit/c3f7c523c97be3f34fd71f70dce1991f39ffad52) to save and retrieve the full remote user info.

We had really no idea what we were doing, but saw similar logic in other Pluggable Auth Providers. Open an issue if you wish to discuss.

### Resources
- https://oauth2-client.thephpleague.com/usage/
- https://github.com/thephpleague/oauth2-client
- https://github.com/wikimedia/mediawiki-extensions-JWTAuth


## Description

The **WSOAuth** extension enables you to delegate authentication to an OAuth provider. It provides a layer on top of PluggableAuth to allow authentication via a number of OAuth providers.

This extension requires PluggableAuth to be installed first. It also requires some PHP libraries, which may be installed using Composer.

Additional information about the extension and how to use it can be found on it's [MediaWiki page](https://www.mediawiki.org/wiki/Extension:WSOAuth).
