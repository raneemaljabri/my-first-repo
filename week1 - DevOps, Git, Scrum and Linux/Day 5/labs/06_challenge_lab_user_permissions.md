# Challenge Lab: Users, Groups, Permissions, and Ownership



## Learning Objectives

By the end of this lab, students will:

- Demonstrate their understanding of user and group management.
- Apply advanced file permission concepts.
- Configure ownership and access controls for specific use cases.
- Solve real-world scenarios involving Linux file security.



## Scenario:

Your company has a project team working on confidential files. The team includes two primary users, `developer1` and `developer2`, and one administrator, `admin_user`. Your task is to create the necessary users, groups, and directory permissions to meet the following requirements:



## Requirements

1. User and Group Management:
   - Create three users: `developer1`, `developer2`, and `admin_user`.
   - Create a group named `project_team` and add both `developer1` and `developer2` to it.
   - Ensure `admin_user` has administrative privileges over the project files.

2. Directory Structure:
   - Create a directory named `/project_data`.
   - Inside `/project_data`, create two subdirectories:
     - `team_files`: Accessible only by members of `project_team`.
     - `admin_files`: Accessible only by `admin_user`.

3. File Permissions:
   - Files created in `team_files` should:
     - Inherit the `project_team` group ownership.
     - Be writable by any group member.
   - Files created in `admin_files` should:
     - Be accessible only by `admin_user`.

4. Ownership and Access Control:
   - Set the appropriate ownership and permissions for `team_files` and `admin_files` to ensure compliance with the above requirements.
   - Prevent users outside of `project_team` from accessing any content in `/project_data`.

5. Special Permissions:
   - Configure the `setgid` bit for the `team_files` directory so that all files and subdirectories created within inherit the group ownership.

6. Verification:
   - Provide evidence that the directory structure, permissions, and ownership meet the requirements by:
     - Listing the directory structure with ownership and permissions.
     - Demonstrating access or denial of access for the users involved.



## Notes:
- Students must ensure they follow the principle of least privilege.
- Documentation of commands used and their purposes is required.
