## Compose Code Convention

    ├── components                  # Shared Components: [Dialog, View, Widget]
    ├── feature           
    │   ├── components              # Folder with components of current screen
    │   │   ├── AuthButtonWidget    # Authorize button
    │   │   ├── AuthCardWidget      # Card, which contains two fields: Login and Password
    │   │   └── AuthSuccessDialog   # Dialog, which is showed after successfull auth
    │   ├── preview                 # Folder with Preview
    │   │   └── AuthScreenPreview   # Preview of Auth screen
    │   ├── AuthScreen              # Authorize Screen which use State Hoisting
    └── └── AuthScreenComponent     # Authorized Screen Component which accept ViewModel