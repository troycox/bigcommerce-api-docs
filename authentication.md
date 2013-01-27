## Overview

The API currently supports Basic access authentication. Connections to the API must be made with a secure HTTPS connection. Credentials should consist of a valid username and their associated API token. See the [Enabling API Access](#api_access) section below for instructions on obtaining an API token. If the credentials are invalid or not supplied, then a 401 Unauthorized response will be sent.

## <a id="api_access"></a>Enabling API Access
To grant a user access to the API, first from your store's control panel then following these steps:

Navigate to the Users area.

1. Edit the user you want to allow access to the API.
2. Scroll down to the Enable the API? setting and tick the Yes, allow this user to use the API tick box.
3. An access token will be generated and shown below.
4. Copy the token.
5. Click the Save button.

## Disabling API Access
If you need to revoke API access for a user you can disable access you can by following these steps:

1. Navigate to the Users area.
2. Edit the user you want to revoke access to the API for.
3. Remove the tick in the Yes, allow this user to use the API tick box.
4. Click the Save button.

## Revoking API Access
If you need to revoke access to an application or integration which currently knows your API token, you can regenerate it by following these steps:

1. Navigate to the Users area.
2. Edit the user you want regenerate the API Token for.
3. Click the Regenerate API Token link under the input box which displays the current token.
4. Copy the token.
5. Click the Save button.
6. The new token will only take effect when the Save button is pressed. Any existing application or integration will now have its access revoked.

## Configuring Permissions
You can allow or disallow user access to certain resources or particular actions on those resources by configuring the permissions through the users Add/Edit screen in the control panel. The same permissions used to control access within the control panel will be used by the API.

Each resource page lists the permissions required to perform each request type for that resource. If a user doesn't have access to a particular resource, then a 403 Forbidden response will be sent.