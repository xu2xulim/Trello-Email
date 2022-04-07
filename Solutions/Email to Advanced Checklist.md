# Email to Advanced Checklist

This solution is built using CloudMailin and a Deta Base application. While can be deployed to Deta, it is current deployed as a service on Wayscript.

The pre-requisites includes :
- a valid registration of the board with your Trello credentials. Note that the credentials are kept in a [Deta Base](https://docs.deta.sh/docs/base/about/).
  - Your data in Deta Base is encrypted and stored safely on AWS. Encryption keys are managed by AWS; AWS manages Exabytes of the world's most sensitive data.
- an CloudMailin email address that forwards to the endpoint sending the email in json normalized format. This will be provided to upon completion of the registration.

## Endpoints

### / (the base URL to be provided upon registration)

This serves as the endpoint for the CloudMailin SMTP to http service.

### /register

This to register the Trello board and your Trello credentials.

## Usage

The following is an outline for creating an advanced checklist on a new card.

- Create an email
- Address it to the CloudMailin Email
- Add the board id to as the subject of the email. e.g. Subject : 5fdd53039a97d380e792101e
  - You can get the board id by appending **.json** to the board url e.g. `https://trello.com/b/CkgNRQgc/dojo-1.json` The resulting screen show the board json file and the board id is the first string e.g. `{"id":"5fdd53039a97d380e792101e","name":"Dojo 1","desc":""....`
- Create a **numbered list** in the email body starting with serial number **1. ** . Most email would have this built in capability.
- Each item on the list will consist of :
  - checklist item name e.g. Check the registration
  - a assigned member username e.g. @superhuman
  - a due date e.g. %2022-05-13
  - Putting it together : Check the registration status @superhuman %2022-05-13
- A new card cardname = **"New Card"** will be create on the first list on the board and the checklist name is **"Email to Advanced Checklist"**.

### Notes
- Have a space between the item name, member username and the due date.
- Item name is mandatory.
- Username and due dates are Optional.
- *DO NOT* use **@ or %** as part of the item name.
- The order for username and due date is not critical.
- While date format shown in the example is YYYY-MM-DD, it should not matter but you should test it.
- Technically there is no limit on the number of items.

### Test Results
The following has been tested successfully :
- Gmail
