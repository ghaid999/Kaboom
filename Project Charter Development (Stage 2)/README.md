# Kaboom! — Project Charter

## 1. Project Objectives

### Project Purpose

Kaboom! is a physical robot paired with a mobile application that helps people maintain focus during study or work sessions. The robot uses a camera and Computer Vision to detect focus-related behaviors and provides real-time feedback. Users can also earn rewards for completing focus sessions.

The project aims to combine Computer Vision, mobile development, hardware, and gamification into a practical prototype that can help users build better focus habits.

## SMART Objectives

1. **Real-Time Focus Detection:** Build a robot that uses a camera and Computer Vision to detect whether a user is Focused, Distracted, or Away during a focus session. The system should identify the correct state in at least 80% of test cases across 5 different users. This should be completed during the development phase of the project, so users can become aware of losing focus and get back on track.

2. **Mobile App and Rewards:** Deliver a mobile app connected to the backend that lets users start and end a focus session with a timer, view a session summary (duration and percentage of focused time), and earn coins after each completed session, with all three core flows working without critical bugs before the integration phase ends. This gives users visible progress and motivation to keep building the habit.

3. **Integrated MVP:** Integrate the 3D-printed robot, Computer Vision module, mobile app, and backend into one MVP that completes a full session (start, detection, robot feedback, reward, progress view) in at least 9 out of 10 test runs, and reaches an average usefulness rating of 4 out of 5 from at least 5 test users by the end of the testing phase, followed by a live demo at the final presentation. This proves the concept works end to end and that users find it valuable.

---

## 2. Stakeholders and Roles

### Stakeholders

| Stakeholder | Type | Role / Interest |
|---|---|---|
| Project Team | Internal | Designs, develops, tests, and documents the Kaboom! MVP. |
| Mentor | External | Provides guidance and evaluates the project based on the project requirements and deliverables. |
| Users | External | Students, employees, and other people who want to improve their focus. They provide feedback about the usability and usefulness of the system. |

### Team Roles

| Team Member | Role                  | Main Responsibilities                                                                          |
| ----------- | --------------------- | ---------------------------------------------------------------------------------------------- |
| **Shahd**   | Project Manager / Computer Vision   | Coordinate the team, organize meetings, track progress, and help manage project tasks.         |
| **Gheed**   | Frontend / AI  | Develop the Computer Vision component and focus-detection logic.                               |
| **Lama**    | Backend / Testing    | Develop the backend, database, and communication between the application and other components. |
| **Noura**   | Backend / Database | Develop the mobile application interface and user experience.                                  |

The team will collaborate through GitHub, project management tools, regular meetings, and shared documentation.

---

## 3. Scope

### In-Scope

The following features and activities are included in the MVP:

* A physical robot prototype.
* A simple 3D-printed robot body.
* Camera integration.
* Basic Computer Vision for detecting focus-related behaviors.
* A mobile application.
* User focus sessions and timers.
* Displaying focus-session information and progress.
* A basic reward system using points or coins.
* Basic robot feedback through expressions or a small screen.
* Communication between the robot, application, and backend where required.
* Testing the system with users and collecting feedback.
* Project documentation and demonstration.

### Out-of-Scope

The following features are outside the scope of the initial MVP:

* Detection of basic states such as:

  * Focused
  * Distracted
  * Away
* Advanced human behavior recognition.
* Full emotional recognition.
* Voice-based personal assistant features.
* Complex robot movement or navigation.
* Large-scale production hardware.
* Integration with commercial meeting or productivity platforms.
* Storing or uploading users' raw camera recordings.
* Advanced AI personalization.
* A large-scale commercial deployment.

These features may be considered for future versions if there is enough time and resources.

---

## 4. Risks and Mitigation Strategies

| Risk                               | Potential Impact                                                            | Mitigation Strategy                                                                                                                         |
| ---------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Computer Vision accuracy**       | The robot may incorrectly detect whether the user is focused or distracted. | Start with simple and measurable behaviors such as face presence and head orientation. Test the system with different users and conditions. |
| **Hardware integration problems**  | Hardware issues could delay development and testing.                        | Use simple hardware components and test each component separately before integration.                                                                                                                 |
| **Integration between components** | The robot, mobile application, and backend may not communicate correctly.   | Define interfaces early and test communication between components throughout development.                                                   |
| **Limited hardware resources**     | The team may face limitations with available components or equipment.       | Build a simple prototype using readily available components and avoid unnecessary hardware features.                                        |

---

## 5. High-Level Plan

The project will be completed over **12 weeks** across five stages, following the Portfolio Project Meetings Plan.

| Week        | Stage                                          | Main Activities / Deliverables                                                                                              |
| ----------- | ---------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Week 1**  | **Stage 1: Team Formation & Idea Development** | Form the team, discuss and evaluate project ideas, select the Kaboom! concept, and define the initial MVP.               |
| **Week 2**  | **Stage 2: Project Charter Development**       | Define project objectives, stakeholders and roles, scope, risks and mitigation strategies, and the high-level project plan. |
| **Week 3**  | **Stage 3: Technical Documentation**           | Create user stories, Figma mockups, high-level system architecture, and database design.                                    |
| **Week 4**  | **Stage 3: Technical Documentation**           | Create sequence diagrams, API specifications, SCM and QA plans, and document technical justifications.                      |
| **Week 5**  | **Stage 4: MVP Development & Execution**       | Set up the frontend, backend, database, GitHub repositories, project management board, and deployment. Begin development.   |
| **Week 6**  | **Stage 4: MVP Development & Execution**       | Complete authentication and the main/home screen functionality where applicable.                                            |
| **Week 7**  | **Stage 4: MVP Development & Execution**       | Complete approximately 50% of the main Kaboom! feature.                                                                  |
| **Week 8**  | **Stage 4: MVP Development & Execution**       | Complete 100% of the main Kaboom! feature.                                                                               |
| **Week 9**  | **Stage 4: MVP Development & Execution**       | Complete secondary features and integrate required third-party services.                                                    |
| **Week 10** | **Stage 4: MVP Development & Execution**       | Perform unit and integration testing and complete optional features if time allows.                                         |
| **Week 11** | **Stage 5: Project Closure**                   | Prepare the project poster, final presentation, and landing page.                                                           |
| **Week 12** | **Stage 5: Project Closure**                   | Final project check-up, review remaining tasks, and complete final preparations.                                            |

### Project Stages

**Stage 1 — Team Formation & Idea Development**
Duration: 1 week

**Stage 2 — Project Charter Development**
Duration: 1 week

**Stage 3 — Technical Documentation**
Duration: 2 weeks

**Stage 4 — MVP Development & Execution**
Duration: 6 weeks

**Stage 5 — Project Closure**
Duration: 2 weeks

**Total Duration: 12 weeks**


## Project Success Criteria

The Kaboom! MVP will be considered successful if the team can demonstrate a working system in which:

* A user can start a focus session.
* The camera can detect basic focus-related behaviors.
* The robot provides feedback based on the detected state.
* The user can view their focus-session progress through the mobile application.
* The user can receive rewards after completing focus sessions.
* The main components work together as one demonstrable MVP.


## Document Authors and Contributors

- Ghaid 
- Lama
- Noura
- Shahd
