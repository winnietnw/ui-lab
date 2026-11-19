# ui-lab

This repository contains my work for the ITDS362 Automated UI Testing Lab.

## Selected Tool Parts
- Part 3: Robot Framework
- Part 4: Cypress

## Part 3: Robot Framework
The `robot/` folder contains Robot Framework test cases, resource files, and test execution results for QuickPizza.

To run the tests:
```bash
cd robot
robot pizza_scenario.robot
```

## Part 4: Cypress
The `cypress/` folder contains Cypress configuration, E2E test files, support commands, screenshots, and videos.

To run all tests:
```bash
cd cypress
npx cypress run --browser chrome
```