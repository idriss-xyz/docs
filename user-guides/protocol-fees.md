# Protocol Fees

This section provides an overview of fees charged by the IDriss protocol. All the values are modifiable and eventually will be subject to updates through decentralized governance.

### IDriss Send Fees

The fees charged by the [IDriss Send](https://www.idriss.xyz/send) protocol differ depending on whether the recipient is a registered IDriss name and whether you send an individual or a batch transfer through MultiSend.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

**Additional clarifications:**

* Who is paying the fees?
  * Fees for transfers to registered IDriss names are deducted from the transfer amount (paid by the recipient).
  * Fees for transfers to unregistered recipients are added to the transfer amount (paid by the sender).
* Fees for batch transfers to a mix of registered and unregistered recipients are calculated by summing up fees from respective tables.
* Sending assets to a mix of registered and unregistered recipients is handled by two separate smart contracts and requires confirming two transactions.
* All fees are charged in MATIC on the Polygon network, except for individual transfers to registered IDriss names. In this case they are charged in MATIC or ERC-20 tokens on Polygon, BNB or ERC-20 tokens on BNB Chain, and ETH or ERC-20 tokens on Ethereum, depending on what coin and network you are using.
* The same fee structure applies to sending payments on Twitter through our [browser extension](https://chrome.google.com/webstore/detail/idriss/fghhpjoffbgecjikiipbkpdakfmkbmig).

### IDriss Book Fees

The [IDriss Book](https://www.idriss.xyz/) protocol charges a one-time fee of $10 per registered address for a lifetime. It can be paid in MATIC on Polygon, BNB on BNB Chain, or ETH on Ethereum.

The registration fee is waived for partner projects who enable [registering new address book records](https://github.com/idriss-crypto/ts-library#3-registering-new-records) inside their dApps.
