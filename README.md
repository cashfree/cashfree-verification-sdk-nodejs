# Cashfree VRS Node SDK
![GitHub](https://img.shields.io/github/license/cashfree/cashfree-verification-sdk-nodejs) ![Discord](https://img.shields.io/discord/931125665669972018?label=discord) ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/cashfree/cashfree-verification-sdk-nodejs/main) ![GitHub release (with filter)](https://img.shields.io/github/v/release/cashfree/cashfree-verification-sdk-nodejs?label=latest) ![npm](https://img.shields.io/npm/v/cashfree-verification) ![GitHub forks](https://img.shields.io/github/forks/cashfree/cashfree-verification-sdk-nodejs) [![Coverage Status](https://coveralls.io/repos/github/cashfree/cashfree-verification-sdk-nodejs/badge.svg?branch=)](https://coveralls.io/github/cashfree/cashfree-verification-sdk-nodejs?branch=main)

The Cashfree VRS Node SDK offers a convenient solution to access [Cashfree VRS APIs](https://docs.cashfree.com/reference/verification-api-overview) from a server-side JavaScript  applications. 



## Documentation

Cashfree's Verification Suite API Documentation - https://docs.cashfree.com/reference/verification-api-overview

Learn and understand verification workflows at Cashfree Payments [here](https://docs.cashfree.com/docs/verification-suite-introduction)

Try out our interactive guides at [Cashfree Dev Studio](https://www.cashfree.com/devstudio) !

## Getting Started

### Installation
```bash
npm i cashfree-verification
```
### Configuration

```javascript 
import { Cashfree } from "cashfree-verification"; 

Cashfree.XClientId = "<x-client-id>";
Cashfree.XClientSecret = "<x-client-secret>";
Cashfree.XEnvironment = Cashfree.Environment.SANDBOX;
```

Generate your API keys (x-client-id , x-client-secret) from [Cashfree Merchant Dashboard](https://merchant.cashfree.com/merchants/login)

### Basic Usage
VoterId Verification
```javascript
var request = {
    "verification_id": 'uniqueVerificationId',
    "epic_number": 'UAI4574761',
    "name": 'John Doe',
}

Cashfree.VrsVoterIdVerification(request).then((response) => {
    console.log('Verification Response:', response.data);
})
.catch((error) => {
    console.error('Error in verification request:', error);
});
```

Liveliness Check
```javascript
const image = fs.createReadStream(<path-to-image>);
Cashfree.VrsLivelinessCheck("uniqueVerificationId",image).then((response) => {
    console.log('Verification Response:', response.data);
})
.catch((error) => {
    console.error('Error in verification request:', error);
});
```


## Supported Resources


## Licence

Apache Licensed. See [LICENSE.md](LICENSE.md) for more details
