# FocusRobot — Technical Documentation

## 1. User Stories and Mockups

### User Stories (MoSCoW)

### Must Have
1. As a user, I want to register as a new user, so that I can create an account and use the application.

2. As a user, I want to log in with my email and password, so that I can securely access my account, my robot, and my session history.

3. As a user, I want to connect my mobile app to the robot, so that the app can communicate with and control my robot during focus sessions.

4. As a user, I want to start a focus session and select a target duration, so that I can begin working with a clear, time-bound goal.

5. As a user, I want the robot to detect whether I'm FOCUSED, DISTRACTED, or AWAY, so that my attention is tracked accurately without manual input.

6. As a user, I want the robot's screen to show a facial expression matching my current focus state, so that I get immediate, non-intrusive feedback.

7. As a user, I want to see my live session status in the mobile app, so that I can monitor progress alongside the robot's feedback.

8. As a user, I want to receive coins when I complete a session, so that I feel rewarded for staying focused.

9. As a user, I want the app to confirm when a session ends (completed or cut short), so that I know the outcome clearly.
   
10. As a user, I want to spend earned coins to customize the robot with clothes and accessories, so that I feel a sense of progression and ownership.

11. As a user, I want a short summary after each session (e.g., time focused vs. distracted), so that I understand how well I actually focused.

### Should Have
1. As a user, I want to view a history of past sessions, so that I can track my focus trends over time.

2. As a user, I want to pause a session, so that I can take a short break without losing my progress or streak.

3. As a user, I want different expression "themes" for the robot, so that I can personalize how it communicates with me.

### Could Have
1. As a user, I want to set daily or weekly focus goals, so that I can build consistent study habits.

2. As a user, I want to compare my stats with friends, so that I stay motivated through light competition.

3. As a user, I want a gentle audio or light cue when I'm distracted, so that I can self-correct without a jarring interruption.

### Won't Have
1. As a user, I want the robot to physically move or gesture, so that it feels more lifelike — out of scope for a simple 3D-printed prototype.

2. As a user, I want the robot to sync with third-party calendars, so that sessions are scheduled automatically.

3. As a user, I want multiple user profiles on one robot, so that my family/roommates can each track their own sessions.

4. As a user, I want voice control, so that I can start/stop sessions hands-free.

### Mockups

Interactive Figma prototype: [FocusRobot (Kaboom) Mockups](https://www.figma.com/design/av0ip8R6icJggihhZaXFMo/Kaboom-?node-id=1-3&p=f&t=6P1tw5wPOf7ddRQe-0)

#### Mockup overview

| Screen | Preview | Covers |
|---|---|---|
| Sign Up | <img width="150" alt="Sign Up" src="https://github.com/user-attachments/assets/a60ecd3b-781d-4c3d-bed6-c49424335a4d" /> | Must Have 1 (register) |
| Login | <img width="150" alt="Login" src="https://github.com/user-attachments/assets/23ba9c4f-9ff7-4c64-8cc9-919ce6e38ef0" /> | Must Have 2 (account access) |
| Connect | <img width="150" alt="Connect" src="https://github.com/user-attachments/assets/67e5ed13-36e7-472f-b559-8dc335fcdbbc" /> | Must Have 2 (pair the robot with the app) |
| Homepage | <img width="150" alt="Homepage" src="https://github.com/user-attachments/assets/4f299bfb-7811-422a-894d-9448eb4c5bfc" /> | Must Have 3 (select a target duration and start a session) |
| Focused Status in Session | <img width="150" alt="Focused Status in Session" src="https://github.com/user-attachments/assets/860256c4-7c4d-44d6-a810-256556cab2f2" /> | Must Have 4, 5, 6 (focus state, expression, live status) |
| Distracted Status in Session | <img width="150" alt="Distracted Status In Session" src="https://github.com/user-attachments/assets/c8cd5bac-148f-450f-8499-35d024223bbb" /> | Must Have 4, 5, 6 |
| Session Complete | <img width="150" alt="Session Complete" src="https://github.com/user-attachments/assets/1eaabad5-b1d0-4781-810e-c2e1966662bf" /> | Must Have 7, 8, 10 (coins earned, outcome, summary) |
| Shop | <img width="150" alt="Shop" src="https://github.com/user-attachments/assets/26fbf6d8-7cc6-4935-8273-0be1bbb42e6a" /> | Must Have 9 (spend coins on hats, screens and effects) |


# FocusRobot: Components, Classes, and Database Design

**Tech stack:** MySQL 8 (database)

---

## Table of Contents

1. [System Architecture](#1-system-architecture)
2. [Class Diagram](#2-class-diagram)
3. [ER Diagram](#3-er-diagram)
4. [Database Schema (MySQL 8)](#4-database-schema-mysql-8)


---
## 1. System Architecture

```mermaid
flowchart TB
    User(["USER"])

    Frontend["<b>FRONTEND</b><br/>Flutter<br/><br/>• Login / Register<br/>• Focus Session<br/>• Timer<br/>• Robot Status<br/>• Rewards / Store"]

    subgraph Cloud["Cloud Hosting"]
        Backend["<b>BACKEND</b><br/>Spring Boot<br/><br/>• Authentication<br/>• Session Management<br/>• Robot Management<br/>• Reward Management"]
        DB[("<b>DATABASE</b><br/>MySQL<br/><br/>• Users<br/>• Robots<br/>• Sessions<br/>• Events<br/>• Rewards<br/>• Store")]
    end

    subgraph Robot["Robot Device"]
        Pi["<b>RASPBERRY PI 4</b><br/><br/>• OpenCV<br/>• MediaPipe<br/>• Focus Detection<br/>• Robot Control"]
        Camera["Camera"]
        Screen["Screen<br/>(facial expressions)"]
    end

    Behavior(["User Behavior"])

    User <-->|"uses app"| Frontend
    Frontend <-->|"REST API + WebSocket<br/>requests / live status"| Backend
    Backend <-->|"SQL<br/>read / write"| DB
    Backend <-->|"WebSocket<br/>commands / focus states"| Pi
    Behavior -->|"observed"| Camera
    Camera -->|"video frames<br/>(stay on device)"| Pi
    Pi -->|"expression"| Screen
```

## 2. Class Diagram

```mermaid
classDiagram
    class User {
        +int id
        +string name
        +string email
        -string passwordHash
        +int coins
        +string role
        +datetime createdAt
        +register() bool
        +login() bool
        +update() bool
        +delete() bool
        +addReward(amount) void
        +buy(productId) bool
    }

    class Admin {
        +addProduct(product) bool
    }

    class FocusSession {
        +int sessionId
        +int userId
        +int robotId
        +int plannedDurationSeconds
        +datetime startTime
        +datetime endTime
        +int durationSeconds
        +int pausedSeconds
        +float focusedPercentage
        +int rewardEarned
        +string status
        +startSession() void
        +endSession() void
        +pauseSession() void
        +continueSession() void
        +calculateReward() int
        +sessionSummary() dict
    }

    class StateLog {
        +int id
        +int sessionId
        +string state
        +datetime startedAt
        +datetime endedAt
    }

    class Robot {
        +int robotId
        +int userId
        +string currentExpression
        +string connectionState
        +updateExpression(state) void
        +connect() bool
    }

    class ComputerVision {
        +bool eyesDetection
        +string state
        +detectState() string
    }

    class Product {
        +int id
        +string name
        +int price
        +string description
        +bool isAvailable
        +getProducts()$ list
    }

    class Purchase {
        +int id
        +int userId
        +int productId
        +int pricePaid
        +datetime purchasedAt
    }

    User <|-- Admin
    User "1" --> "0..1" Robot : owns
    User "1" --> "0..*" FocusSession : starts
    Robot "1" --> "0..*" FocusSession : runs
    FocusSession "1" --> "0..*" StateLog : records
    Robot "1" --> "1" ComputerVision : uses
    ComputerVision ..> StateLog : provides state
    User "1" --> "0..*" Purchase : makes
    Purchase "0..*" --> "0..*" Product : for
    Admin ..> Product : manages
```

---

## 3. ER Diagram

```mermaid
erDiagram
    USERS ||--o| ROBOTS : owns
    USERS ||--o{ FOCUS_SESSIONS : starts
    ROBOTS ||--o{ FOCUS_SESSIONS : runs
    FOCUS_SESSIONS ||--o{ STATE_LOGS : has
    USERS ||--o{ PURCHASES : makes
    PRODUCTS ||--o{ PURCHASES : "bought in"

    USERS {
        int id PK
        varchar name
        varchar email UK
        varchar password_hash
        int coins
        enum role "user or admin"
        tinyint admin_flag UK "generated, NULL for non-admin"
        datetime created_at
    }

    ROBOTS {
        int id PK
        int user_id FK, UK
        enum current_expression "happy, sad, confused"
        enum connection_state "connected, disconnected"
    }

    FOCUS_SESSIONS {
        int id PK
        int user_id FK
        int robot_id FK "nullable"
        int planned_duration_seconds
        datetime start_time
        datetime end_time "nullable"
        int duration_seconds
        int paused_seconds
        decimal focused_percentage "nullable"
        int reward_earned
        enum status "active, paused, completed"
    }

    STATE_LOGS {
        bigint id PK
        int session_id FK
        enum state "focused, distracted, away"
        datetime started_at
        datetime ended_at "nullable"
    }

    PRODUCTS {
        int id PK
        varchar name
        int price
        text description "nullable"
        boolean is_available
    }

    PURCHASES {
        int id PK
        int user_id FK
        int product_id FK
        int price_paid
        datetime purchased_at
    }
```

**Relationships**

- User 1 : 0..1 Robot
- User 1 : N FocusSession
- Robot 1 : N FocusSession
- FocusSession 1 : N StateLog
- User M : N Product (through `purchases`)

---

## 4. Database Schema (MySQL 8)

Create the tables in this order because of the foreign keys.

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password_hash VARCHAR(255) NOT NULL,
    coins INT NOT NULL DEFAULT 0 CHECK (coins >= 0),
    role ENUM('user','admin') NOT NULL DEFAULT 'user',
    admin_flag TINYINT GENERATED ALWAYS AS (IF(role = 'admin', 1, NULL)) VIRTUAL,
    created_at DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    UNIQUE KEY uq_single_admin (admin_flag)
);

CREATE TABLE robots (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL UNIQUE,
    current_expression ENUM('happy','sad','confused') NOT NULL DEFAULT 'happy',
    connection_state ENUM('connected','disconnected') NOT NULL DEFAULT 'disconnected',
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);

CREATE TABLE focus_sessions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    robot_id INT NULL,
    planned_duration_seconds INT NOT NULL DEFAULT 1800,
    start_time DATETIME NOT NULL,
    end_time DATETIME NULL,
    duration_seconds INT NOT NULL DEFAULT 0,
    paused_seconds INT NOT NULL DEFAULT 0,
    focused_percentage DECIMAL(5,2) NULL,
    reward_earned INT NOT NULL DEFAULT 0,
    status ENUM('active','paused','completed') NOT NULL DEFAULT 'active',
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
    FOREIGN KEY (robot_id) REFERENCES robots(id) ON DELETE SET NULL
);

CREATE TABLE state_logs (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    session_id INT NOT NULL,
    state ENUM('focused','distracted','away') NOT NULL,
    started_at DATETIME NOT NULL,
    ended_at DATETIME NULL,
    FOREIGN KEY (session_id) REFERENCES focus_sessions(id) ON DELETE CASCADE
);

CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    price INT NOT NULL CHECK (price > 0),
    description TEXT NULL,
    is_available BOOLEAN NOT NULL DEFAULT TRUE
);

CREATE TABLE purchases (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    product_id INT NOT NULL,
    price_paid INT NOT NULL,
    purchased_at DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
    FOREIGN KEY (product_id) REFERENCES products(id) ON DELETE RESTRICT
);
```
```mermaid
sequenceDiagram
    actor User
    participant App as Mobile App
    participant Backend as Spring Boot Backend
    participant DB as MySQL Database
    participant Robot as Robot

    User->>App: Select target duration
    App->>Backend: Start focus session
    Backend->>DB: Create focus session
    DB-->>Backend: Session created
    Backend->>Robot: Start monitoring
    Robot-->>Backend: Monitoring started
    Backend-->>App: Session started
    App-->>User: Display active session
```
```mermaid
sequenceDiagram
    participant Camera
    participant Robot as  Robot
    participant CV as OpenCV / MediaPipe
    participant Backend as Spring Boot Backend
    participant DB as MySQL Database
    participant App as Mobile App
    participant Screen as Robot Display

    Camera->>Robot: Capture video frames
    Robot->>CV: Process video frame
    CV->>CV: Detect focus state

    alt User is focused
        CV-->>Robot: FOCUSED
        Robot->>Screen: Display focused expression
    else User is distracted
        CV-->>Robot: DISTRACTED
        Robot->>Screen: Display distracted expression
    else User is away
        CV-->>Robot: AWAY
        Robot->>Screen: Display away expression
    end

    Robot->>Backend: Send focus state
    Backend->>DB: Save focus event
    Backend-->>App: Send live focus status
    App-->>User: Display current focus state
```
```mermaid
sequenceDiagram
    actor User
    participant App as Mobile App
    participant Backend as Spring Boot Backend
    participant DB as MySQL Database

    User->>App: Complete focus session
    App->>Backend: Send session completion
    Backend->>Backend: Calculate reward
    Backend->>DB: Update user's coins
    Backend->>DB: Save reward
    DB-->>Backend: Reward saved
    Backend-->>App: Send earned coins
    App-->>User: Display earned coins
```

---

## 4. API Mapping

| Action | Endpoint |
|---|---|
| Register / Login | `POST /auth/register` / `POST /auth/login` |
| User data | `GET/PUT/DELETE /users/me` |
| Robot | `POST /robot/connect`, `GET /robot` |
| Start session | `POST /sessions` |
| Pause / Continue / End | `PATCH /sessions/{id}/pause`, `/continue`, `/end` |
| History and summary | `GET /sessions`, `GET /sessions/{id}` |
| Products | `GET /products`, `POST /products` (admin) |
| Purchase | `POST /purchases` |
