//EVM, Ethereum Virtual Machine
//Ethereum, Polygon, Artitrum, Optimum, Zksync



// SPDX-License-Identifier: MIT 
pragma solidity 0.8.19;

contract Skipperman {
    // myFavoriteNumber gets initialized to 0 if no number is written
    uint256 myFavoriteNumber;

    struct Person {
        uint256 favoriteNumber;
        string name;
    }

    // Dynamic array of Person structs
    Person[] public listOfPeople;

    mapping(string => uint256) public nameToFavoriteNumber; 

    Person public Skip = Person({favoriteNumber: 27, name: "Skip"});
    Person public Nas = Person({favoriteNumber: 2, name: "Nas"});
    Person public Cookie = Person({favoriteNumber: 1, name: "Cookie"});
   
    function store(uint256 _favoriteNumber) public {
        myFavoriteNumber = _favoriteNumber;
    }

    //view, pure
    function retrieve() public view returns(uint256) {
        return myFavoriteNumber;
    }

    // calldata, memory, storage
    function addPerson(string memory name, uint256 _favoriteNumber) public {
        listOfPeople.push( Person({favoriteNumber: _favoriteNumber, name: name}) );
        nameToFavoriteNumber[name] = _favoriteNumber; // corrected variable name
    }

}

