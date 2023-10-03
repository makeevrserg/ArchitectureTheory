## Gradle Project structure

    ├── XXX-gradle-project          # Other gradle projects/subprojects/build-logic
    ├── YYY-gradle-project          # Other gradle projects/subprojects/build-logic
    ├── instances            
    │   ├── app                       # Android app instance
    │   ├── desktop                   # Desktop app instance
    │   └── wear                      # Wear os instance
    ├── modules
    │   ├── components                  
    │   |   ├── UserComponent         # Component which provides current user
    │   |   └── XXXXXX                # Other component
    │   ├── features                  
    │   |   ├── Splash                # Splash feature
    │   |   └── XXXXXX                # Some other feature
    │   ├── services                  
    │   |   ├── resources             # Shared resources
    │   |   └── XXXXXX                # Some other service module

### 1. XXX-gradle-project

Here's stored other gradle projects which included in the root project

**Example**: build-logic, custom included git repo

### 2. instances

Here's stored application instances for various platform: android, ios, desktop etc...

### 3. modules

App-specific modules stored here

### 4. :modules:services

Service modules can only be dependent on each other

Service modules can't have ViewModel's, but can have basic implementation of it

**Example**:

- :services:resource - contains all resources for application
- :services:core - contains shared functions for all features, BaseViewModel etc...
- :services:api-backend - contains auto-generated backend api

### 5. :modules:features

Feature modules can't be dependent on each other (ideally)

Feature modules can see services modules and components modules

Feature module is an implementation for some feature, Splash screen, Auth screen etc...

Ideally feature module should contain only one entry point, which can be Composable screen for example

### 6. :modules:components [EXPERIMENTAL]

Components are required to make feature modules fully independent of each others

Components modules can't be dependent on each other

Components modules is a set of reusable logic or ui parts

For example - UserComponent, which will be singleton and provides user information - Authorized, Not authorized, send
events - Token Expired and etc
