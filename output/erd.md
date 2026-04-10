erDiagram
  USERS {
    int id PK
    string name
    string email
    string password
  }
  PRODUCTS {
    int id PK
    string name
    float price
    int stock
  }
  ORDERS {
    int id PK
    int user_id FK
    float total
    string status
  }
  PAYMENTS {
    int id PK
    int order_id FK
    float amount
    string status
  }
  USERS ||--o{ ORDERS : places
  ORDERS ||--o{ PAYMENTS : has
  ORDERS }o--|| PRODUCTS : contains