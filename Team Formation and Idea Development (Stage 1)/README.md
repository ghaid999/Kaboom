# Stage 1 Report

## Team Formation and Idea Development

### Project: Kaboom!

**Team Members:** Shahd, Gheed, Lama, Noura

---

# 1. Team Formation Overview

## 1.1 Team Members and Initial Roles

| Team Member | Initial Role    | Strengths / Interests      | Stage 1 Contribution                   |
| ----------- | --------------- | -------------------------- | -------------------------------------- |
| Shahd       | Project Manager | Organization, coordination | Meeting coordination and documentation |
| Gheed       | Hardware Developer | Robotics, hardware | Researching hardware components and planning hardware integration |
| Lama        | Backend & Testing | Backend development, testing | Backend development and initial system testing |
| Noura       | Frontend Developer | UI/UX, frontend development | Designing and developing the user interface |

> **Note:** Roles are initial roles and may change during development depending on the project's technical requirements and each member's interests.

## 1.2 Collaboration Strategy

| Area             | Our Agreement                                 |
| ---------------- | --------------------------------------------- |
| Communication    | Discord, WhatsApp                             |
| Documentation    | Notion, Google Docs                           |
| Code Management  | GitHub, VS Code, IntelliJ IDEA                |
| Task Tracking    | GitHub Projects, Notion                       |
| Meeting Schedule | 4 days a week                                 |
| Decision Making  | Team discussion and majority vote when needed |

Our team will communicate regularly, document important decisions, and use GitHub to keep the development work organized. Tasks will be divided based on team members' strengths while allowing everyone to contribute to different parts of the project.

---

# 2. Research and Brainstorming

## 2.1 Research Approach

Our team began by identifying real problems we experience in our daily lives and areas where we believed technology could provide a useful solution.

We brainstormed several ideas and evaluated each one based on the problem it addresses, its target users, existing solutions, technical feasibility, and potential for future development.

For each idea, we also considered whether similar products or platforms already exist. When existing solutions were found, we looked for possible improvements or gaps that could make our idea different.

This process helped us compare different concepts and identify the idea that best matched our team's interests, skills, and project timeline.

## 2.2 Brainstorming Methods

We used the following brainstorming approaches:

* **Mind Mapping:** We started with common problems and expanded them into possible technology-based solutions.
* **Group Discussion:** Each team member proposed ideas and explained the problem, target users, and possible features.
* **Problem-Based Brainstorming:** We focused on problems we personally observed rather than starting with a specific technology.
* **Competitor Research:** We searched for existing solutions to understand what already exists and identify possible gaps.
* **Feasibility Discussion:** We discussed whether each idea could realistically be developed by four developers within the project timeline.

## 2.3 Ideas Explored


| **Idea** | **Description** | **Strengths** | **Weaknesses / Challenges** | **Decision** | **Reason for Decision** |
|---|---|---|---|---|---|
| **Kaboom!** | A physical robot paired with a mobile app that helps users maintain focus during study or work sessions. The robot uses a camera and Computer Vision to monitor focus-related behaviors and provides feedback and rewards. | Combines Computer Vision, mobile development, hardware, and gamification. It provides an opportunity to build a physical prototype and has potential for future expansion. | Computer Vision accuracy, hardware integration, privacy concerns, and limited development time. | **Selected** | The idea combines current technologies such as AI, Computer Vision, and robotics. It also provides a challenging project that allows the team to learn new technologies and build a physical prototype. |
| **ArSL** | A real-time Arabic Sign Language interpreter for meetings that converts spoken language into Arabic Sign Language. | Addresses an important accessibility problem and has potential social impact. | Integration with existing meeting platforms such as Zoom, Teams, and Meet could create adoption and technical challenges. | Rejected | Similar solutions already exist, which makes it more difficult for the project to provide a sufficiently different or unique solution. |
| **Masar** | A platform for discovering activities in Saudi Arabia and creating personalized itineraries based on user preferences. | Useful for people looking for activities, potentially budget-friendly, and can provide personalized recommendations. | Similar platforms and services already exist, making differentiation more difficult. | Rejected | Similar platforms and services already exist, so the team felt it would be difficult to provide enough differentiation from existing solutions. |
| **Hackathon Platform** | A platform for discovering hackathons and finding suitable teammates based on skills and interests. | Useful for students and developers interested in hackathons and could include team matching. | Finding reliable and consistent hackathon data and building a useful matching system within the project timeline could be challenging. | Rejected | The idea was considered feasible, but the team preferred Kaboom! because it is more challenging and provides more opportunities to explore hardware, AI, and robotics. |
| **Team-Based Word Game** | A multiplayer team-vs-team Arabic word game inspired by category-based games. Players compete in teams by answering word or knowledge challenges under time limits, with different rounds and scoring mechanics. | Simple and engaging concept, suitable for multiplayer, encourages teamwork and competition, and can be expanded with different game modes and challenges. | Similar word and category games already exist, making differentiation more difficult. Multiplayer synchronization and game balancing would also add development complexity. | Rejected | The idea was considered too simple compared with the team's goal of building a more challenging project that allows them to learn and apply new technologies. |

# 3. Idea Evaluation

## 3.1 Evaluation Criteria

We initially evaluated the ideas using the following criteria:

* **Feasibility:** Can the idea realistically be developed within three months?
* **Prototypability:** Can we build and demonstrate a working prototype?
* **Data Availability:** Can we access the data or tools required?
* **Technical Challenge:** Does the project provide an appropriate technical challenge for the team?
* **Problem Relevance:** Does the idea address a real problem?
* **Scalability:** Does the idea have opportunities for future development?

Each criterion was scored from 1 to 5.

## 3.2 Evaluation Matrix

| Idea               | Feasibility | Prototypable | Data / Tools Available | Technical Challenge | Real Problem | Scalability | Total |
| ------------------ | ----------: | -----------: | ---------------------: | ------------------: | -----------: | ----------: | ----: |
| Kaboom!         |           3 |            5 |                      4 |                   5 |            5 |           5 | **27** |
| ArSL               |           3 |            3 |                      4 |                   5 |            4 |           4 | **23** |
| Masar              |           4 |            5 |                      4 |                   3 |            3 |           4 | **23** |
| Hackathon Platform |           3 |            5 |                      2 |                   4 |            4 |           4 | **22** |
| Team-Based Word Game |         5 |            5 |                      4 |                   2 |            2 |           3 | **21** |

> The scores represent the team's initial assessment during brainstorming. They are not intended to be an objective measurement of the quality of the ideas. The final decision also considered team interest, learning opportunities, hardware experimentation, and the ability to create a demonstrable prototype.

---

# 4. Selected MVP Concept

## 4.1 MVP Summary

### Kaboom!

Kaboom! is a **physical desktop robot paired with a mobile application** designed to help users maintain focus during study or work sessions.

The user starts a focus session through the application and selects a target duration. During the session, the robot uses a camera and Computer Vision techniques to detect focus-related behaviors such as face presence, eye state, and head orientation.

The system converts these observations into simple focus states such as:

* `FOCUSED`
* `DISTRACTED`
* `AWAY`

The robot provides visual feedback through a small screen displaying different facial expressions.

After successfully completing a focus session, the user receives rewards such as XP or coins. These rewards can later be used to customize the robot with different clothes, accessories, and other items.

The MVP will focus on a simple physical prototype rather than a complex moving robot. The body can be 3D printed, while a small computer such as a Raspberry Pi can connect the camera and screen.

---

## 4.2 Problem Statement and Target Users

| Field                 | Response                                                                                                                                                                   |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Problem Statement** | Many people find it difficult to maintain focus for extended periods, especially when studying or working in environments with frequent distractions. |
| **Target Users**     | Students, employees, and anyone who wants to improve their focus and build better focus habits.                                                                                                                                                                   |
| **Expected Impact**   | Encourage users to maintain longer and more consistent focus sessions through real-time feedback and rewards.                                                              |

---

## 4.3 Key MVP Features

The MVP will keep the number of features limited so that the team can build and test them properly within the project timeline.

| Feature             | What It Enables                                                 | Priority    |
| ------------------- | --------------------------------------------------------------- | ----------- |
| User Accounts       | Registration, login, and user profile                           | Must Have   |
| Focus Timer         | Set a focus duration and track session progress                 | Must Have   |
| Computer Vision     | Detect face presence, eye state, and head orientation           | Must Have   |
| Focus Detection     | Convert CV information into focused, distracted, or away states | Must Have   |
| Physical Robot      | Provide real-time feedback through the robot                    | Must Have   |
| Reward System       | Give XP/coins for completed focus sessions                      | Must Have   |
| Robot Customization | Use rewards to customize the robot                              | Should Have |
| Focus History       | Display previous sessions and progress                          | Should Have |

### Initial Computer Vision Scope

The first version will focus on a small number of detectable behaviors:

1. **Face Presence**

   * Detect whether the user is in front of the camera.

2. **Eye State**

   * Detect whether the user's eyes are open or closed.

3. **Head Orientation**

   * Estimate whether the user is facing the screen or looking away.

4. **Time-Based Focus Logic**

   * Avoid treating a single blink or short movement as a distraction.
   * Use the duration of a detected behavior before changing the focus state.

Additional features such as phone detection, yawning detection, or detecting another person may be considered for future versions.

---

# 5. Why We Chose This MVP

We selected Kaboom! because it combines several areas that our team wants to learn and practice, including Computer Vision, mobile application development, backend development, databases, hardware integration, and 3D printing.

The project also allows us to create a physical prototype that can be demonstrated during the final presentation rather than building only a software interface.

Although the project includes hardware and Computer Vision challenges, we can control the scope by starting with a simple robot consisting of a 3D-printed body, camera, small screen, and Raspberry Pi.

Another important factor was the opportunity to expand the project in the future. The initial MVP can focus on basic focus detection, while later versions could include additional Computer Vision features, improved personalization, more robot interactions, and additional customization options.

The idea also addresses a problem that is relevant to our target users: maintaining focus during study and work.

---

# 6. Challenges and Opportunities

| Area                 | Challenge / Opportunity                                                                        | Planned Response                                                                                        |
| -------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Computer Vision**  | Detecting focus accurately from camera information can be difficult.                           | Start with a small set of measurable behaviors such as face presence, eye state, and head orientation.  |
| **Hardware**         | Integrating the camera, screen, Raspberry Pi, and 3D-printed body may require experimentation. | Build and test each hardware component separately before integrating the complete robot.                |
| **Scope**            | Combining mobile development, CV, backend, and hardware can become too large.                  | Keep the MVP limited to the core focus session flow and simple robot interactions.                      |
| **Time**             | Hardware development may take longer than expected.                                            | Build the software and CV prototype first while developing the hardware in parallel.                    |
| **Gamification**     | Rewards can make the experience more engaging.                                                 | Implement XP/coins and a small number of customization items in the MVP.                                |
| **Future Expansion** | The robot can support additional capabilities later.                                           | Design the system so additional sensors, CV features, and interactions can be added in future versions. |

---

# 7. Decision-Making Summary

After brainstorming and researching multiple ideas, the team compared the ideas based on feasibility, prototyping potential, available tools and data, technical challenge, problem relevance, and scalability.

Kaboom! was selected because it provides a clear MVP that can be demonstrated physically while allowing the team to work across multiple technical areas.

The team also considered the project's development timeline and decided to control the scope by starting with a simple physical robot and a limited Computer Vision system.

The final concept is therefore:

> **A physical robot companion connected to a mobile application that helps users maintain focus during study or work sessions through Computer Vision, real-time feedback, and a reward system.**

---

# 8. MVP Scope

To keep the project achievable within the development period, the first version will include:

```text
Mobile App
    │
    ├── User Account
    ├── Focus Timer
    ├── Session Progress
    └── Rewards
            │
            ▼
      Focus Detection
            │
       Computer Vision
            │
            ▼
       Physical Robot
       ├── Camera
       ├── Screen
       ├── Raspberry Pi
       └── 3D Printed Body
```

The MVP will **not** initially include complex robot movement, advanced conversation, or a large number of Computer Vision behaviors. These features can be considered after the core system is working.

---

# 9. Conclusion

Stage 1 established the team's initial roles, collaboration strategy, brainstorming process, evaluated ideas, and selected MVP.

The team selected Kaboom! as a project that combines software, Computer Vision, hardware, and gamification while addressing the problem of maintaining focus during study and work.

The next stage will focus on validating the problem, defining detailed requirements, and creating the technical plan needed to begin development.

## Document Authors and Contributors

- Ghaid 
- Lama
- Noura
- Shahad
