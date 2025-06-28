# Tenant and User Course Management Feature

## Overview
This feature enables multi-tenant management for course-based video platforms. Key elements:
- Tenants: Organizations/teams with their own courses and users.
- Users: Can belong to one/more tenants
- Courses: Created under a tenant.
- Members: Assigned to tenants and courses, with granular permissions.

### Functional Requirements
- Create tenants
- Add users to tenants
- Create courses under tenants
- Assign members to courses
- Members with course access can view videos
- Tenant creator (admin) can delete videos

## Mermaid Diagram (Permissions & Relationships)
```mermaid
flowchart TD
    A[Tenant] -->|has| B(Course)
    A -->|has| C(Member/User)
    B -->|has| D(Video)
    C -->|is assigned to| B
    subgraph Permissions
        C1[Admin (Tenant Creator)]
        C2[Course Member]
    end
    A -- grants --> C1
    B -- grants --> C2
    C1 -- can --> E[Delete Video]
    C2 -- can --> F[View Video]
```

## Related Issues
- [Implement Tenant and User Course Management](https://github.com/janakiramg/demo-stream/issues/7)
- [Permission Levels: Tenant Admin vs Course Member](https://github.com/janakiramg/demo-stream/issues/8)
- [Bug: Restrict Course Video Access to Explicit Members](https://github.com/janakiramg/demo-stream/issues/9)

## Reference
See [Ideas.md](Ideas.md) for potential future permission roles and extensibility.