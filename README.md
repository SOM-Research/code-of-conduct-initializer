# Code of Conduct Initializer GitHub Action

This GitHub Action handles scenarios for missing Code of Conduct or outdated Contributor Covenant version by creating or updating the `CODE_OF_CONDUCT.md` file and creating a pull request.

## Features

- Checks for missing `CODE_OF_CONDUCT.md` and creates one if absent.
- Updates the `CODE_OF_CONDUCT.md` to the latest Contributor Covenant version if outdated.
- Creates a pull request for the changes made to the `CODE_OF_CONDUCT.md`.

## Inputs

- `USER_GITHUB_TOKEN` **(required)**: User GitHub Token for authentication and pushing changes.
- `EVENT_ACTION` **(required)**: Event action that triggered the workflow, used to determine the appropriate response.

### How It Works
1. **Checkout Repository**: The action checks out the repository to get the latest code and context.
2. **Configure Git User**: Sets up the Git user configuration for committing changes.
3. **Authenticate for Git Operations**: Authenticates to GitHub for fetching and pushing branches.
4. **Create or Switch to Branch**: Creates or switches to a branch based on the event action (`no_code_of_conduct` or `handle_contributor_covenant_1_4`).
5. **Add or Update `CODE_OF_CONDUCT.md`**: Copies the template `CODE_OF_CONDUCT.md` file to the repository and stages it for commit.
6. **Commit Changes**: Commits the changes with an appropriate message based on the event action.
7. **Push Changes**: Pushes the committed changes to the corresponding branch.
8. **Set Pull Request Environment Variables**: Sets environment variables for the pull request title, body, and branch.
9. **Create Pull Request**: Uses the `vsoch/pull-request-action` to create a pull request for the changes.

## Example Scenario
- **Missing Code of Conduct**: The action will add a `CODE_OF_CONDUCT.md` file and create a pull request.
- **Outdated Code of Conduct**: The action will update the `CODE_OF_CONDUCT.md` to the latest version and create a pull request.

## Permissions
This action requires the following permissions:

- `contents: write`
- `issues: write`
- `pull-requests: write`

Ensure these permissions are set in your workflow.

## License
This work is licensed under a Creative Commons Attribution-ShareAlike 4.0 International License.

The CC BY-SA license allows users to distribute, remix, adapt, and build upon the material in any medium or format, so long as attribution is given to the creator. The license allows for commercial use. If you remix, adapt, or build upon the material, you must license the modified material under identical terms.

[Creative Commons License](https://creativecommons.org/licenses/by-sa/4.0/)

## Author
Created by CobosDS. For any issues or contributions, please open an issue or submit a pull request on the [GitHub repository](https://github.com/SOM-Research/code-of-conduct-initializer).
