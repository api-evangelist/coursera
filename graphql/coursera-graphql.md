# Coursera GraphQL Schema

## Overview

Coursera is a global online learning platform offering courses, specializations, professional certificates, and degrees from top universities and companies. The platform serves learners, instructors, and institutional partners worldwide.

Coursera's public-facing API is REST-based (OAuth 2.0), documented at https://building.coursera.org/app-platform/docs/. There is no official public GraphQL endpoint. This conceptual GraphQL schema is derived from Coursera's documented REST catalog API, affiliate API, partner documentation, and publicly observable platform capabilities.

## Schema Source

- REST Catalog API: https://api.coursera.org/api/courses.v1
- Developer Documentation: https://building.coursera.org/app-platform/catalog/
- GitHub Organization: https://github.com/coursera
- Platform: https://www.coursera.org/

## Design Notes

- Schema follows GraphQL best practices with scalar types, enums, interfaces, and pagination via connection/edge patterns.
- All IDs are `ID` scalars mapping to Coursera's internal slug-based or UUID identifiers.
- Nullable fields reflect data that may be absent depending on course type or enrollment state.
- The schema covers 65+ named types spanning catalog, enrollment, learning progress, assessments, community, credentials, and career outcomes.

## Key Domain Areas

### Catalog
`Course`, `Specialization`, `Degree`, `OnlineDegree`, `Partner`, `University`, `InstructorProfile`, `SkillTag`, `SearchResult`, `Recommendation`

### Enrollment and Progress
`CourseEnrollment`, `SpecializationEnrollment`, `CohortEnrollment`, `ProgressSummary`, `Milestone`, `LearnerGoal`, `LearnerPath`

### Curriculum Structure
`Module`, `Lesson`, `Lecture`, `Quiz`, `QuizQuestion`, `GradedItem`, `Assignment`, `AssignmentSubmission`, `ProgrammingAssignment`

### Assessment and Grading
`CourseGrade`, `PeerReview`, `PeerReviewAssignment`

### Community
`ForumThread`, `ForumPost`, `Discussion`, `Announcement`

### Credentials
`Certificate`, `CourseraPlus`, `LearnerBadge`

### Workspace
`Workspace`, `WorkspaceSession`, `Notebook`

### Career
`CareerOutcome`, `SalaryData`

### Cohort and Scheduling
`Cohort`, `CohortSchedule`

### Localization
`Translation`

## Type Count

65+ named types including scalars, enums, interfaces, object types, input types, and connection/edge wrappers.
