# Kaboom!
 
Kaboom! is a desktop robot paired with a mobile app that helps people stay focused during study or work sessions. The robot watches through its camera, decides whether the user is **Focused**, **Distracted**, or **Away**, shows a matching face on its screen, and the app rewards completed sessions with coins that can be spent on robot accessories.
 
Holberton School Software Engineering, 3rd Semester Portfolio Project.
 
## Tech Stack
 
| Layer | Technology |
| --- | --- |
| Mobile app | Flutter |
| Backend API | Spring Boot (REST + STOMP WebSocket), own JWT authentication |
| Database | MySQL 8 |
| Robot | Raspberry Pi 4, Python, OpenCV, MediaPipe, 3D printed body |
 
## Project Documentation
 
| Stage | Document |
| --- | --- |
| Stage 1 · Team Formation and Idea Development | [Stage 1 Report](<Team Formation and Idea Development (Stage 1)/README.md>) |
| Stage 2 · Project Charter | [Project Charter](<Project Charter Development (Stage 2)/README.md>) |
| Stage 3 · Technical Documentation | [Technical Documentation](<Technical Documentation (Stage 3)/README.md>) |
| Stage 4 · MVP Development and Execution | In progress |
| Stage 5 · Project Closure | Not started |
 
Design mockups: [Figma](https://www.figma.com/design/av0ip8R6icJggihhZaXFMo/Kaboom-?node-id=1-3&p=f&t=6P1tw5wPOf7ddRQe-0)
 
## Repository Structure
 
```text
Kaboom/
├── README.md
├── Team Formation and Idea Development (Stage 1)/
├── Project Charter Development (Stage 2)/
├── Technical Documentation (Stage 3)/
├── backend/        Spring Boot API (Stage 4)
├── mobile/         Flutter app (Stage 4)
└── robot/          Raspberry Pi focus detection (Stage 4)
```
 
The `backend/`, `mobile/`, and `robot/` folders are created during Stage 4 setup. Each will have its own README with setup and run instructions.
 
## Branching
 
`main` holds stable, demo ready code. `develop` is the integration branch. New work goes in `feature/<name>`, `fix/<name>`, or `docs/<topic>` branches and is merged into `develop` through a pull request with one approval. See [SCM and QA Plan](<Technical Documentation (Stage 3)/README.md#6-scm-and-qa-plan>).
 
## Team
 
| Member | Role |
| --- | --- |
| Shahd | Project Manager · Computer Vision |
| Gheed | Frontend · AI |
| Lama | Backend · Testing |
| Noura | Backend · Database |
 
