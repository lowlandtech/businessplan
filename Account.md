#### Account

An account replaces the concept of identity in the CardStrip network. In most blockchain the concept identity is circumvented by use of private public key pairs. But those blockchains don't account for reputation and rely on external systems to lend trust to a transaction for which that blockchain records a payment.

CardStrip seeks to reintroduce or internalize that form of trust by offering a reputation system based on accounts and account keys. Such a reputation was first pioneered by eBay in the early 2000s by allowing sellers and buyers to give feedback on a transaction they were involved in. The system proved to be hugely successful and made eBay's success possible by allowing future sellers a buyers to examine a user's reputation history before considering to transact with them.

An account is a decentralized attempt to introduce such a feedback system on transactions into the blockchain. Taking advantage of the ability to create [Hierachical Deterministic Keys](https://bitcoin.org/en/developer-guide#hierarchical-deterministic-key-creation) will allow CardStrip to generate an account key from a private key. This account key which for all intend and purposes is a public derived key but can also be used to independently generate child public keys. These child public keys can then be used to sign account state mutations. Verifications of these account state changes can be done by using the private key that generated the account key.

#### Account state

Account state is an encrypted json object that lives on the blockchain. Every transaction lists the smartcontract that needs to be executed and the result conditions that need to be met before the transaction can be considered valid.

Night Spiria

#### Card Hierarchies and Cardchain

Every account maintains its own chain of public cards.



````json
{
  "trxid": "s4th5s4dgg45gh4ds56fhg4gd65h4df"
  "paymentid": "some text", 
  {
  	"in":"fdhy489jgh1d6st4jfdt4g9duj8trj"
  	"amount": "42657895125"
  }
}
````



#### Account State Machine

* [Stateless](https://github.com/dotnet-state-machine/stateless)
* [DOT](https://en.wikipedia.org/wiki/DOT_(graph_description_language))
* [Reactive](https://github.com/Reactive-Extensions/Rx.NET)

