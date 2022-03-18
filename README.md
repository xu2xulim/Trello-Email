# Trello-Email

Trello offers a couple of email related services/solutions. They include :

- Email from Trello automation

This sends email message as part of Trello automation.

- Email to board

This creates a new card on a predetermined list on a board. It adds labels, members and attachments to the card with the text portion of the email subject as the card name and the email body as card description.

- Email to card comment

This adds a comment using the email subject and email body.

For more details of the last two capabilities see https://help.trello.com/article/809-creating-cards-by-email

- Email solutions with Power Ups

The options available here include Gmail, Mail for Trello (previously know as Sendboard), Gmail by Cardbox, BenkoBooard (Gmail support only) and Contalist

## Custom built email solutions

The following are custom built email solutions :

### Email to Board Plus

As the name suggests, it implements the capabilities of Trello email to board and some additional features including :

- adds card start and due
- converts number list from email body to Checklists
- cards can be created for any list on any board with a single custom email address

It uses CloudMailin to send the email message to a Deta Micro. The configuration is stored in a Deta Base. It requires an admin user API Key and Token to be kept in the .env folder on the micro.

Since the entire email content is available to the endpoints, the application can be modified for specific needs e.g. to display the sender email address on the card description.

#### Endpoints

### /

This serves as the webhook endpoint for the CloudMailin SMTP to http service.

### /setup

This is used to setup the destination board and list for each CloudMailin email account.

The endpoint documentation is available at https://wy9u2s.deta.dev/redoc

### Email to Card Plus

This solution is built using Contalist, CloudMailin and a Deta Micro application.

The pre-requisites includes :
- embed a the {cardid} on the email e.g **Our Card Reference : IuyU5CS5**
- an internal reference for email filter to forward email to the CloudMailin email address e.g. **Internal Reference : 9acbc162ecfd92db3272**

Using Contalist, the above can be built into email templates.

With the pre-requisites in place, the additional capabilities of this solution included :
- create the comment using the email subject and body on **any card**. There is no need to share Trello card email address
- adds attachment(s) to the card, if this is included in the email.
- Since the entire email content is available to the endpoint, the application can be modified for specific needs e.g. to display the sender email address on the card description.

#### Endpoints

### /

This serves as the webhook endpoint for the CloudMailin SMTP to http service.
