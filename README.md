pragma solidity >=0.6.0 <0.9.0;

contract SimpleStorage{
    // uint256 accountBalance = 0;
    uint256 public favoriteNumber;
    string food;
    
    struct People{
        uint256 favoriteNumber;
        string name;
    }
    
    People[] public people; 
    
    mapping(string => uint256)public nameToFavouriteNumber;
    // People public person = People({favoriteNumber:2,name:'patric'});
    
    function store(uint256 _favoriteNumber) public{
        favoriteNumber = _favoriteNumber;
    }
    
    // function ATM (uint256 _amount) public{
    //     accountBalance += _amount;
    //     // return _message;
    // }
    
    // function NewAccountBalance () public view returns(uint256){
    //     return accountBalance;
    // }
    
    function retrive() public view returns(uint256){
        return favoriteNumber;
    }

    function addPerson(string memory _name,uint256 _favoriteNumber) public{
     
        people.push(People( _favoriteNumber,_name));
                             
        nameToFavouriteNumber[_name]=_favoriteNumber;
       
    }
}
