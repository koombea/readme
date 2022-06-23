> :warning: **This template contain descriptions of each of the sections with examples**  
  Please read and follow them as much as needed for each PR.  
  Place this template in `.github/pull_request_template.md` in the repository to be rendered as the default PR template for the project.  
  Remove this quote session when adding this tempalte to the project.  

[Based on the Readme template defined in https://github.com/koombea/koombea_rails_best_practices/blob/develop/wiki/Sample%20PR%20Template.md]: text
[Place this template in ".github/pull_request_template.md" in the repository to be rendered as the default PR template for the project]: text
[Title: Add a brief description of the card developed, include the Card IDs related to the change]: text
[Example: KOO-271 Add Soft deletion to Users]: text

## Background

### Associated Stories
[Add a Link and a description of the tickets related to the this PR]: text
[Example: Jira KOO-271 : Add active scope to user model(<link_to_Jira_ticket>)]: text
* [Jira [KOO-000]: Title_of_the_card_worked](<link_to_Jira_ticket>)

### Overview
[Describe the funcitonalities, fixes and improvements done in this PR]: text
[Example: "Add deleted_at field to users, Add scope to get list of active users, etc"]: text

* Funcitonality_description_1
* Funcitonality_description_2

### Visual Documentation
[Add Screenshot, GIFs or videos displaying the functionalities added]: text
[Describe how these are related to the functionalities if needed]: text
N/A

## Review

### QA Steps
[Describe the step to reproduce the acceptance criteria of the card]: text
[If needed, apply optional scenarios as well]: text
[Example: "Open a console., Create user with deleted_at not nil., Check the user you just created is not in the list, etc"] : text
* [ ] step_1
* [ ] step_2

## Deployment

### Environment variables Changes
[Describe the enviariables and or secrets that need to be added to the environments before or after the changes are deployed]: text
[Provide the values of the vars unless the data is private, separate these between environments if needed]: text
[Add the new env variable `USER_ACTIVE_SCOPE=true`]: text
* [ ]  add_env_variable_1
* [ ]  add_env_variable_2

### Non-Code Changes
[Describe tasks that need to be run when the changes these changes are deployed to specific environments]: text
[Example: "Run data migration to update inactive users's deleted_at `rake users:soft_delete_inactives` "]: text
* [ ] Run_task_before_or_after_deploy_1
* [ ] Run_task_before_or_after_deploy_2

### Other Notes
[Describe extra notes about accesses, credentials or users creation, or any other tasks not related to code itself]: text
[Example: "I will need someone with access to the console to get this command run when this is deployed to prod."]: text
* Other_note_1