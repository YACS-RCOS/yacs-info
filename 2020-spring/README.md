# Spring 2020

## Goals

### User System

At the current moment, it appears the most important project to finish is the user system. This will enable us to collect data to then provide the administration about improving and observing course selection before the courses hit SIS.

Some key things left to finish/change:
- Deployment into docker composition _in progress_
- Collection of user data (meta data) [browser, computer, ip, ...]
- Change to passwordless authentication (email only) _needs design_

### Course Tags [Search]

**Pending Decision**

To follow along with the idea of making course scheduling easier, targeting higher level courses, a key problem is selecting courses that meet graduation requirements. For example, as a CS student, I want to be able to know which courses are **communication intensive classes** so that I can meet the requirement in order to graduate on-time. To do this we would need to persist course data and annotate in collaboration with the administration or through manual tagging.

For this to be possible it would require:
- Persistent Data (Across Semesters)
- Ability to tag courses in db
- Filtering in search on tags and majors

### [Technical] Consolidate Technology

Transition code from Ruby to Python to enable all CS students to understand and contribute to YACS easily. At the moment, not many devs on the team know Ruby which makes managing the project and code more difficult that it needs to be. Additionally, having a micro-services architecture increases the operational complexity to distribute the code to other schools and manage local and production deployments.

#### Action (i): Migrate to Python

Cost:
- Time
- Lost code

Benefits:
- Long term maintainability of project
- Larger recruitment potential

#### Action (ii): Migrate to less services

Cost:
- Slower dev speed (More merge conflict)

Benefit:
- Lower integration costs (network vs code integration)
- Info transfer between team (fixing: Member A works on X, Member B works on Y, Member A leaves, Member B cannot work on Y)
  - More collaboration, More learning within the team
