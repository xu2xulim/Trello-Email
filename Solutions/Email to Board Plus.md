# Email to Board Plus

As the name suggests, it implements the capabilities of Trello email to board and some additional features including :

- adds card start and due
- converts number list from email body to Checklists
- cards can be created for any list on any board with a single custom email address

It uses CloudMailin to send the email message to a Deta Micro. The configuration is stored in a [Deta Base](https://docs.deta.sh/docs/base/about/). It requires an admin user API Key and Token to be kept in the .env folder on the micro.

Since the entire email content is available to the endpoints, the application can be modified for specific needs e.g. to display the sender email address on the card description.

## Endpoints

### /

This serves as the webhook endpoint for the CloudMailin SMTP to http service.

### /setup

This is used to setup the destination board and list for each CloudMailin email account.

The endpoint documentation is available at https://wy9u2s.deta.dev/redoc
