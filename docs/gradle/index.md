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

### 1. **Other gradle projects**

`:XXX-gradle-project` can be any other gradle project which included in the root project

**Example**: build-logic, custom included git repo

### 2. **Instances**

`:instances` store application instances for various platform: android, ios, desktop etc...

### 3. **Modules**

`:modules` store app-specific modules

### 4. **Services**

`:modules:services` can only be dependent on each other

`:modules:services` can be dependent on other gradle projects as they represent custom library

`:modules:services` modules can't have ViewModel's, but can have basic implementation of it

`:modules:services` is basically utilities for application

**Example**:

- `:services:resource` - contains all resources for application
- `:services:core` - contains shared functions for all features, BaseViewModel etc...
- `:services:api-backend` - contains auto-generated backend api

### 5. **Features**

`:modules:features` Ideally can't be dependent on each other

`:modules:features` can see services modules and components modules

`:modules:features` is an implementation for some feature, Splash screen, Auth screen etc...

`:modules:features` Ideally should contain only one entry point, which can be Composable screen for example

### 6. **Components [EXPERIMENTAL]**

`:modules:components` are required to make feature modules fully independent of each others

`:modules:components` modules can't be dependent on each other

`:modules:components` modules is a set of reusable logic or ui parts

#### Want to see more detailed? Use navigation on left!