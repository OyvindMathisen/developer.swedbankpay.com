### Card Problems

There are a few problems specific to the `creditcard` resource that you may want
to guard against in your integrations. All credit card problem types will have
the following URI structure:

`https://api.payex.com/psp/errordetail/creditcard/<error-type>`

#### Contractual Problem Types

{:.table .table-striped}
| Type                           | Status | Description                                                                                                                    |
| :----------------------------- | :----: | :----------------------------------------------------------------------------------------------------------------------------- |
| `cardbranddisabled`            | `403`  | The card brand is disabled.                                                                                                    |
| `accountholdertyperejected`    | `403`  | The account holder type is rejected.                                                                                           |
| `cardtyperejected`             | `403`  | The card type is rejected.                                                                                                     |
| `3dsecurerequired`             | `403`  | The transaction was rejected by 3-D Secure.                                                                                    |
| `authenticationstatusrejected` | `403`  | The authentication status was rejected.                                                                                        |
| `frauddetected`                | `403`  | The transaction was fraudulent.                                                                                                |
| `3dsecuredeclined`             | `403`  | 3-D Secure declined the transaction.                                                                                           |
| `velocitycheck`                | `429`  | Indicates that the limit for how  many times a card or different cards can be used for attempting a purchase has been reached. |

#### Acquirer and 3-D Secure Problem Types

{:.table .table-striped}
| Type                           | Status | Description                                                                                   |
| :----------------------------- | :----: | :-------------------------------------------------------------------------------------------- |
| `3dsecureerror`                | `400`  | 3-D Secure not working. Try again later.                                              |
| `cardblacklisted`              | `400`  | Card blacklisted. The payer needs to contact their card-issuing bank.                            |
| `paymenttokenerror`            | `403`  | There was an error with the payment token.                                                    |
| `carddeclined`                 | `403`  | The card was declined.                                                                        |
| `acquirererror`                | `403`  | The acquirer responded with a generic error.                                                  |
| `acquirercardblacklisted`      | `403`  | Card blacklisted. The payer needs to contact their card-issuing bank                            |
| `acquirercardexpired`          | `403`  | Wrong expire date or card has expired. The payer needs to contact their card-issuing bank.    |
| `acquirercardstolen`           | `403`  | Card blacklisted, the payer needs to contact their card-issuing bank.                            |
| `acquirerinsufficientfunds`    | `403`  | Card does not have sufficient funds, the payer needs to contact their card-issuing bank.        |
| `acquirerinvalidamount`        | `403`  | Amount not valid by acquirer. Contact support.ecom@payex.com.                                   |
| `acquirerpossiblefraud`        | `403`  | Transaction declined due to possible fraud, the payer needs to contact their Card-issuing bank. |
| `3dsecureusercanceled`         | `403`  | Transaction was canceled during 3-D Secure verification.                                        |
| `3dsecuredeclined`             | `403`  | Transaction was declined during 3-D Secure verification.                                         |
| `frauddetected`                | `403`  | Fraud detected. The payer needs to contact their card-issuing bank.                             |
| `badrequest`                   | `500`  | Bad request. Try again after some time.                                                        |
| `internalservererror`          | `500`  | Server error. Try again after some time.                                                       |
| `3dsecureacquirergatewayerror` | `502`  | Problems reaching 3-D Secure verification. Try again after some time.                           |
| `badgateway`                   | `502`  | Problems reaching the gateway. Try again after some time.                                      |
| `acquirergatewayerror`         | `502`  | Problems reaching acquirers gateway. Try again after some time.                                |
| `acquirergatewaytimeout`       | `504`  | Problems reaching acquirers gateway. Try again after some time.                                |
