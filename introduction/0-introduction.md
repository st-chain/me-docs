# Introduction

Me-Hub is a blockchain application built using the Cosmos SDK. It integrates various modules from the Cosmos ecosystem, including Osmosis and Ethermint, and includes custom modules to extend its functionality.

This documentation provides an overview of the project's architecture, modules, and setup instructions.

# Architecture

The Me-Hub application is highly modular, with each module encapsulating specific functionalities. The core components include:

- **Keepers**: Manages various keepers responsible for different modules.
- **Modules**: Integrates various modules from the Cosmos SDK, Osmosis, Ethermint, and custom modules.
- **Initialization**: Functions to initialize keepers and set up the application.
- **Hooks**: Allows inter-module interactions and event handling.

The application is designed for extensibility and interoperability with other blockchains.