# Developers

## Getting Started

In order to run the test suite of Arrakis modular smart contracts, follow these steps:

1. Clone the repository by running:
```
git clone https://github.com/ArrakisFinance/arrakis-modular.git
```
2. Install the required submodules and compile the contracts by running:
```
forge build
```
3. Create `.env` file using `.envExample` as a reference. You can fill in your own alchemy api key (or a different RPC url altogether)
4. Execute the test suite by running:
```
forge test -vv
```

If tests run and pass then your dev environment is set up correctly!