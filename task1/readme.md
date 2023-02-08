# TASK 1: Setup Development Environment

## Installing Rust (with rustup)
Run this script with default installation context
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
After `rust`+`cargo` installed, installer will give prompt **"Rust is installed now. Great!"**.
Reload your shell session.

Example Output Screen:
```
Rust is installed now. Great!

To get started you may need to restart your current shell.
This would reload your PATH environment variable to include
Cargo's bin directory ($HOME/.cargo/bin).

To configure your current shell, run:
source "$HOME/.cargo/env"
```

## Install Wasm
```bash
rustup target add wasm32-unknown-unknown
```
Output:
```
info: downloading component 'rust-std' for 'wasm32-unknown-unknown'
info: installing component 'rust-std' for 'wasm32-unknown-unknown'
 18.9 MiB /  18.9 MiB (100 %)  10.5 MiB/s in  1s ETA:  0s
```****

## Install Cargo-Concordium (Linux Distro)
```bash
wget https://distribution.concordium.software/tools/linux/cargo-concordium_2.7.0 -O cargo-concordium
chmod +x cargo-concordium
mv cargo-concordium ~/.cargo/bin
cargo concordium --help
```
## Install Concordium Client
```bash
wget https://distribution.concordium.software/tools/linux/concordium-client_5.0.2-0 -O concordium-client
chmod +x concordium-client
sudo mv concordium-client /usr/local/bin
concordium-client consensus status --grpc-port 10000 --grpc-ip node.testnet.concordium.com
```
## Install Web Wallet Extension
[See instruction here](https://developer.concordium.software/en/mainnet/net/browser-wallet/setup-browser-wallet.html) and export the private-key
## Export the Account From Webwallet to concordium-client
Import exported account and input the private-key
```bash
concordium-client config account import 4L3WQLjdAhvjey3Kyc7Sdv7Smhe9asLYsksFbWSWFm5b4jX1SA.export --name testnet```
```
Output: 
```
Enter encryption password: 
Loaded the following account from the testnet chain:
- 4L3WQLjdAhvjey3Kyc7Sdv7Smhe9asLYsksFbWSWFm5b4jX1SA 'testnet'.
All signing keys have been encrypted with the password used for this import.
Note that accounts are not transferable between different chains, e.g., from testnet to mainnet or vice-versa.

Adding account 4L3WQLjdAhvjey3Kyc7Sdv7Smhe9asLYsksFbWSWFm5b4jX1SA with name(s) 'testnet'.
Creating directory '/home/khafid/.config/concordium/accounts/4L3WQLjdAhvjey3Kyc7Sdv7Smhe9asLYsksFbWSWFm5b4jX1SA'.
Created key directory.
Writing file '/home/khafid/.config/concordium/accounts/names.map'.
Added name mapping: 'testnet' --> '4L3WQLjdAhvjey3Kyc7Sdv7Smhe9asLYsksFbWSWFm5b4jX1SA'.
Warning: Importing account without a secret encryption key provided. This account will not support encrypted transfers.
The keys were successfully written to disk.

```

## Footnote
Read at: [Concordium Setup the development environment
](http://developer.concordium.software/en/mainnet/smart-contracts/tutorials/setup-env.html)