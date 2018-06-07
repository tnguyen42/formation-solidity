# 1
```javascript
pragma solidity ^0.4.24;

contract CapsuleTemporelle {

}
```

# 2
```javascript
pragma solidity ^0.4.24;

contract CapsuleTemporelle {
	string message;

}
```

# 3
```javascript
pragma solidity ^0.4.24;

contract CapsuleTemporelle {
	string message;

	constructor(string _message) public {
        message = _message;
    }
	function get() public view returns (string _message) {
        return message;
    }
}
```

# 3
```javascript
pragma solidity ^0.4.24;

contract CapsuleTemporelle {
	string message;
	address owner;

	constructor(string _message) public {
        message = _message;
		owner = msg.sender;
    }
	function get() public view returns (string _message) {
        return message;
    }
}
```