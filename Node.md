#### Node

A CardStrip node is a console application that which location needs to be placed in a PATH folder so that it can function as a cli to give access to the CardStrip Network by processing commands.

````shell
c:\> cs wallet new --password ******* --path c:\myWallet.dat
````

Or 

````shell
c:\> cs key new --password ******* --path c:\myWallet.dat
````

The node can also be used to start up the wallet ui.



````shell
c:\> cs --shell true --port 7895
````

The above are the default parameters which the CardStrip cli uses for the user wallet.



#### UnitOfWork

The unit of work combines all the data sources that the current cardstrip node uses to interact with the network, the blockchain and the database.

````c#
var uof = new UnitOfWork();
````

Examples of the Unit of Work interface:

````c#
public interface IUnitOfWork {
  Guid SessionId { get; }
  List<IWallet> Wallets { get; }
  IBlockchain Blockchain { get; }
  IDatabase Database { get; }
  ...
}
````

and 

````c#
uof.Blockchain.Blocks;
uof.Blockchain.Blocks.First().Headers();
uof.Blockchain.Blocks.First().Transactions(); // all transactions recorded in this block ...
uof.Blockchain.Uxtos;
uof.Blockchain.Transactions; // all transactions ever recorded on the blockchain ...
uof.Wallets.First().Transactions; // all transactions made by all the keys in this wallet ...
uof.Wallets.First().Keys;
uof.Wallets.First().Account.Transactions; // all transactions monitored by this account ...
uof.Database.SmartContracts; // all known smartcontracts by this node ...
uof.Database.Cards; // all private and public smartcontract metadata ...
````

The unit of work will be a unified interface to manipulate the node data and all manipulations on it are either extension methods hanging off IUnitOfWork or are of IAction methods that are executed by the wallet job manager.



#### Wallet

To open the wallet,  the wallet location must be given and the wallet password with which the file was encrypted. The UoW knows the following extension method:

````c#
var wallet = uof.OpenWallet("c:/myWallet.dat", "********");
````



After the wallet is loaded one can loop through the keys stored in the wallet.

````c#
foreach(var ppk in wallet.keys){
  Console.Log(ppk.PublicKey());
}

// example output
// 
// 
````

A wallet can store unlimited number of keys.



##### Creating a new wallet

````c#
var wallet = new Wallet("c:/wallet.dat", "*******");
````



##### Generate a new new private public key pair

````c#
var ppk = wallet.NewKey();
ppk.PublicKey();

// example output
//
````

The private key is automatically saved in the wallet file. At this point the node is not aware of the new wallet. A reference to that new wallet must be stored to it before the node can interact with that wallet. A node can store an unlimited number of wallets.



````c#
uof.Wallets.Add(wallet);
````

