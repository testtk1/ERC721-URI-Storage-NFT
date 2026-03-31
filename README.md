# ERC721-URI-Storage-NFT
ERC721 URI Storage NFT
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";

contract URINFT is ERC721URIStorage {
    uint256 public nextId;

    constructor() ERC721("URINFT", "UNFT") {}

    function mint(string memory uri) public {
        _mint(msg.sender, nextId);
        _setTokenURI(nextId, uri);
        nextId++;
    }
}
