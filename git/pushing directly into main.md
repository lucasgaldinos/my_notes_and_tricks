# Problem

I pushed on main without having to create a pull request.

## Solution

It seems that you pushed changes directly to the `main` branch without creating a pull request. This is possible if you have write access to the repository. If you want to make sure that changes go through a review process using pull requests, you can follow these steps:

1. Create a new branch for your changes:

   ```bash
   git checkout -b new-feature
   ```

   Replace `new-feature` with a descriptive name for your branch.

2. Make your changes, add them, and commit:

   ``` bash
   git add .
   git commit -m "Add new feature"
   ```

    Replace "Add new feature" with a meaningful commit message.

3. Push your branch to the remote repository:

   ```bash
   git push origin new-feature
   ```

   Replace `new-feature` with the name of your branch.

   **This is important, as when someone have write acces, it can write directly into main. To avoid, always push to the remote BRANCH, not using the option `git push origin HEAD:main`**

4. Now, go to the repository's web interface (e.g., GitHub, GitLab, Bitbucket), and create a pull request for the `new-feature` branch. This will allow you or other collaborators to review the changes before merging them into the `main` branch.

To prevent direct pushes to the `main` branch in the future, you can set up branch protection rules in the repository settings. This process will vary depending on the platform you're using (e.g., GitHub, GitLab, Bitbucket). In general, you'll need to:

1. Go to the repository settings.
2. Navigate to the section for branch protection or access control.
3. **Set up a rule for the `main` branch that requires pull requests for merging changes. gh (GITHUB CLI) DOES NOT ALLOW TO CHANGE RULES YET, so it must be done in the repo configurations.**

With a branch protection rule in place, you'll ensure that changes to the `main` branch go through a review process using pull requests.
