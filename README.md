# Station Watch Project

This project is developed for managing laboratories, machines, and stations, and is part of the **CENG318 Human Computer Interaction course project**, conducted in collaboration with **Arçelik** through joint meetings.

## Table of Contents

- [Station Watch Project](#station-watch-project)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Setup](#setup)
  - [Usage](#usage)
  - [Example Scenario](#example-scenario)
  - [Project Architecture](#project-architecture)
  - [Roles](#roles)

## Introduction

The Station Watch Project is a backend application designed to manage various aspects of laboratories, machines, and stations. The project is built using **Node.js** and connects to a **MongoDB**.

## Setup

To set up the project locally:

1. **Clone the repository**:

    ```bash
    git clone https://github.com/cerencaglayan/stationwatch.git
    ```

2. **Install the required dependencies**:

    ```bash
    cd stationwatch
    npm install
    ```


3. **Start the application**:

    ```bash
    node app.js
    ```

    The application will run on `localhost:8000`.

## Usage

After starting the application, some of the the following API endpoints can be used:

- **Create a lab**:
    ```http
    POST http://localhost:8000/api/lab
    ```

- **Create or use an existing machine**:
    ```http
    POST http://localhost:8000/api/machine
    ```

- **Create a station**:
    ```http
    POST http://localhost:8000/api/station
    ```

- **Create and assign a test to a station**:
    ```http
    POST http://localhost:8000/api/test
    ```

- **Finish a test**:
    ```http
    PUT http://localhost:8000/api/test/:id/finish
    ```

## Example Scenario

1. **Create a lab**:
    ```http
    POST http://localhost:8000/api/lab
    ```

2. **Select an existing machine or create a new one**:
    ```http
    POST http://localhost:8000/api/machine
    ```

3. **Create a station**:
    ```http
    POST http://localhost:8000/api/station
    ```

4. **Create a test and assign it to a station**:
    ```http
    POST http://localhost:8000/api/test
    ```

5. **Create a second test which will be in a pending state due to no station**:
    ```http
    POST http://localhost:8000/api/test
    ```

6. **Finish the first test, an email will be sent to the creator**:
    ```http
    PUT http://localhost:8000/api/test/:id/finish
    ```

7. **The remaining tasks will be completed subsequently**.

## Project Architecture

- **Main File**: `app.js`
- **Models and Controllers**:
    - `lab`
    - `station`
    - `machine`
    - `test`
    - `user`
    - `component`

## Roles

- **Engineer**: Responsible for creating labs, machines, stations, and tests. They have access to all operations except stopping tests.
- **Technician**: Can only stop tests.