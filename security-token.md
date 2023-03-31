## Example solidity code about "Security token for identification", by full information
Here's an example Solidity code for a security token contract that can be used for identification purposes:
```solidity
pragma solidity ^0.8.0;
contract SecurityToken {

  string public name;
  string public symbol;
  uint256 public totalSupply;
  mapping(address => uint256) public balanceOf;
  mapping(address => mapping(address => uint256)) public allowance;

  event Transfer(address indexed from, address indexed to, uint256 value);
  event Approval(address indexed owner, address indexed spender, uint256 value);

  constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
    name = _name;
    symbol = _symbol;
    totalSupply = _totalSupply;
    balanceOf[msg.sender] = _totalSupply;
  }

  function transfer(address _to, uint256 _value) public returns (bool success) {
    require(balanceOf[msg.sender] >= _value, "Insufficient balance");
    balanceOf[msg.sender] -= _value;
    balanceOf[_to] += _value;
    emit Transfer(msg.sender, _to, _value);
    return true;
  }

  function approve(address _spender, uint256 _value) public returns (bool success) {
    allowance[msg.sender][_spender] = _value;
    emit Approval(msg.sender, _spender, _value);
    return true;
  }

  function transferFrom(address _from, address _to, uint256 _value) public returns (bool success) {
    require(_value <= balanceOf[_from], "Insufficient balance");
    require(_value <= allowance[_from][msg.sender], "Insufficient allowance");
    balanceOf[_from] -= _value;
    balanceOf[_to] += _value;
    allowance[_from][msg.sender] -= _value;
    emit Transfer(_from, _to, _value);
    return true;
  }
}
```

This contract defines a standard ERC-20 token with the name, symbol, and total supply specified in the constructor. Users can transfer tokens to each other and approve other addresses to spend their tokens on their behalf.

This contract can be used for identification purposes by assigning a unique token to each user and verifying ownership of that token. For example, a user could be required to send a small amount of their token to a verification contract to prove that they own it.
