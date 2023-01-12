# Raffle Contract

This is a sample raffle contract that implements the Chainlink VRF Version 2. The contract allows users to enter a raffle by sending a specified amount of ether to the contract's address. Once the raffle has reached a certain time interval or number of players, a random winner is chosen using the Chainlink VRF algorithm.

## Features

- Enter a raffle by sending ether to the contract's address
- Choice of time interval or number of players to trigger the raffle
- Uses Chainlink VRF to randomly pick a winner
- Emits events for entering the raffle and picking a winner

## Usage

1. Instantiate the contract by providing the following parameters:
   - vrfCoordinatorV2: address of the Chainlink VRF Coordinator contract
   - subscriptionId: subscription ID for using the Chainlink VRF service
   - gasLane: key hash for the gas lane
   - interval: time interval (in seconds) between raffles or number of players needed to trigger a raffle
   - entranceFee: amount of ether needed to enter the raffle
   - callbackGasLimit: gas limit for callback function
2. Call the `enterRaffle()` function to enter the raffle. Make sure to send enough ether to meet the entrance fee requirement.
3. Once the raffle is triggered (either by reaching the time interval or number of players), a winner will be picked using the Chainlink VRF algorithm. The winner will be notified and the contract will emit a `WinnerPicked` event with the winner's address.

## Errors

The contract may revert with the following errors:

- Raffle\_\_UpkeepNotNeeded: Raffle upkeep is not needed at the moment.
- Raffle\_\_TransferFailed: Transfer failed.
- Raffle\_\_SendMoreToEnterRaffle: Not enough ether was sent to enter the raffle.
- Raffle\_\_RaffleNotOpen: Raffle is not currently open for entry.

## Note

Please make sure to fund your subscription with LINK before using this contract.

## Author

Adarsh Singh

## License

This contract is licensed under the MIT License.
