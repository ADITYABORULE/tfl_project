# Project Management API Test Cases

| Test Case ID | Test Scenario | Preconditions | Test Steps | Expected Result |
|---------------|---------------|---------------|------------|----------------|
| TC_PROJECT_01 | Verify mentor can view all assigned projects | Mentor logged into system | 1. Send request to `GET /api/mentor/projects` | API returns list of all projects with **project name, status, team members** |
| TC_PROJECT_02 | Verify mentor can view running projects | Mentor logged in | 1. Send request to `GET /api/mentor/projects?status=running` | System returns only projects with status **running** |
| TC_PROJECT_03 | Verify mentor can view completed projects | Mentor logged in | 1. Send request to `GET /api/mentor/projects?status=completed` | System returns only projects with status **completed** |
| TC_PROJECT_04 | Verify invalid project status filter | Mentor logged in | 1. Send request to `GET /api/mentor/projects?status=invalid` | System returns empty list or validation error |
| TC_PROJECT_05 | Verify mentor can view project details | Mentor logged in and project exists | 1. Call `GET /api/mentor/projects/details` with valid projectId | API returns **project description, technologies used, repository link** |
| TC_PROJECT_06 | Verify invalid project ID in details API | Mentor logged in | 1. Call `GET /api/mentor/projects/details` with invalid projectId | System returns **error message or 404 response** |
| TC_PROJECT_07 | Verify mentor can add student to project | Mentor logged in and project exists | 1. Send `POST /api/mentor/projects/{projectId}/students` with studentId | Student added to project team successfully |
| TC_PROJECT_08 | Verify mentor can remove student from project | Mentor logged in and student exists in project | 1. Call `DELETE /api/mentor/projects/{projectId}/students/{studentId}` | Student removed from project team |
| TC_PROJECT_09 | Verify mentor can submit project feedback | Mentor logged in and project exists | 1. Send `POST /api/mentor/projects/{projectId}/feedback` with feedback JSON | Feedback stored successfully |
| TC_PROJECT_10 | Verify mentor can schedule project meeting | Mentor logged in and project exists | 1. Send `POST /api/mentor/projects/{projectId}/meeting` with meeting date and time | Meeting scheduled successfully |




Aditya


