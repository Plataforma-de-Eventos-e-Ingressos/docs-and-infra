```mermaid
erDiagram
    USERS {
        uuid id PK
        string name
        string email UK
        string password_hash
        enum role "ORGANIZADOR, CLIENTE, PORTARIA"
        timestamp created_at
    }

    EVENTS {
        uuid id PK
        uuid organizer_id FK
        string external_api_id "TMDb ou Ticketmaster"
        string title
        timestamp event_datetime
        string location
        decimal price
        int total_capacity
    }

    TICKETS {
        uuid id PK
        uuid event_id FK
        uuid client_id FK
        string seat "Nullable (para pista)"
        enum status "RESERVED, PAID, VALIDATED, CANCELLED"
        string qr_token UK
        timestamp updated_at
    }

    USERS ||--o{ EVENTS : "creates (if Organizer)"
    USERS ||--o{ TICKETS : "buys (if Client)"
    EVENTS ||--o{ TICKETS : "has"
