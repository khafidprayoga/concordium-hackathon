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
```

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
## Create Test Net Account
## Acquiring testnet CCD via the CCD faucet
## Export the Account Form Webwallet to concordium-client


## Footnote
Read at: [Concordium Setup the development environment
](http://developer.concordium.software/en/mainnet/smart-contracts/tutorials/setup-env.html)