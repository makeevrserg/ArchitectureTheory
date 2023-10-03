## In-Feature Architecture Convention

    ├── util                        # Core util package
    ├── feature           
    │   ├── data              
    │   │   ├── model       
    │   │   ├── mapping              
    │   │   │   └── MyMapper    
    │   │   ├── impl              
    │   │   │   └── MyRepositoryImpl    
    │   │   └── MyRepository    
    │   ├── domain              
    │   │   ├── model       
    │   │   ├── mapping      
    │   │   └── usecase  
    │   ├── di              
    │   │   ├── factory              
    │   │   │   └── MyCustomFactory    
    │   │   └── MyModule  
    │   ├── presentation              
    │   │   └── AuthViewModel    
    └── └── util     