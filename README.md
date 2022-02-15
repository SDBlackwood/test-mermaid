# test-mermaid
Test Mermaid

```mermaid
title MEL - JSON -> SQLite

actor Member
Member-->MEL: 1.Navigate to MEL, Enter Mydexid, Password and PK

MEL->MEL: 2. Cache PK

MEL-->PDS: 3. Get JSON Data

MEL-->MEL: 4. Cache JSON Data

Member-->MEL: 5. Navigate to Dataset page
#note left of MEL: Member has JSON data \nand not SQlite data for this datasets

MEL-->PDS: 6. Get SQLite Data

alt 7.1. Member has JSON data for this dataset in cache

loop 7.1.1. FOR each JSON instance
    MEL->PDS: Format/Provision JSON data into SQLite
end
    
else 7.2. Member does not have JSON or SQlite for this dataset
    MEL-->PDS: Provision blank SQLite record
end

MEL-->Member: 8. Display SQlite data
```
