# Nike Shoe Store - Entity Relationship Diagram (ERD)

```mermaid
erDiagram
    PRODUCT {
        int ProductID PK
        string Name
        string Category
        decimal Price
        string Size
        int Stock FK
    }
    CUSTOMER {
        int CustomerID PK
        string FirstName
        string LastName
        string Email
        string Phone
    }
    SALE {
        int SaleID PK
        int CustomerID FK
        int ProductID FK
        date SaleDate
        int Quantity
        decimal TotalAmount
    }
    INVENTORY {
        int InventoryID PK
        int ProductID FK
        int StockLevel
        string Location
    }

    PRODUCT ||--o{ SALE : "is sold in"
    CUSTOMER ||--o{ SALE : "makes"
    PRODUCT ||--o{ INVENTORY : "is stored in"
