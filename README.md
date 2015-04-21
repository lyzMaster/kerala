# Kerala



<img align="right" height="300" src="http://i180.photobucket.com/albums/x247/Mandee_Candee/Palm-Tree-cartoon.gif">

> An IPFS wrapper for string storage and retrieval 

Kerala offers a an easy-to-use wrapper to store and retrieve links on the Interplanetary File System. (IPFS) I created this library to aid me in creating a decentralized twitter. It can be used for any sort of decentralized application that stores user tweets/posts/microblogs.

Kerala


-Converts a user's string input into an IPFS Hash<br />
-Saves the hash to a text file locally<br />
-Takes new string submissions with their associated hashes and links them. It will replace the hash in the local text file with the newest hash, thus creating what is known in IPFS as a MerkleDAG. <br />
-Pulls all users strings using only there single hash stored in their local textfile. The MerkleDAG link in IPFS allows the user to pull all linked strings in a single request<br />
>>>>>>> 9676a9c4b9f018c8a814e2bec6e39751b3977953

## Install

```sh
$ go get -u github.com/siraj/go-kerala/kerala
```

Kerala depends on [IPFS](https://github.com/jbenet/go-ipfs). 

## Usage

```go
//Start a node
node, err := kerala.StartNode()
	if err != nil {
		panic(err)
	}

//Add your text to IPFS (Creates MerkleDAG)
var userInput = r.Form["sometext"]
Key, err := kerala.AddString(node, userInput[0])

//Get all your text from IPFS (Retrieves MerkleDAG)  
tweetArray, _ := kerala.GetStrings(node)
  
```
