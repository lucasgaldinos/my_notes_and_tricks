# Problem

Had to delete branch after the merge into the main branch.

## Solution

To delete the branch, the user must first delete it locally and then delete it remotely.
[As pointed by the user Matthew Rankin](https://stackoverflow.com/a/2003515/17160939), the steps are

1. Delete the local branch:
    `git branch -[d|D] <branchname>`
    Where -D is forced deletion and -d deletes the branch only if it has already been merged. (see git branch -h)
2. Delete the remote branch:
    `git push <remote_name> --delete <branch_name>` or
    `git push <remote_name> :<branch_name>`
    In both cases, the remote branch will be deleted.
3. As pointed by Trevor in the answer commentary: Don't forget to do a `git fetch --all --prune` on other machines after deleting the remote branch on the server. ||| After deleting the local branch with `git branch -d` and deleting the remote branch with `git push origin --delete` other machines may still have "obsolete tracking branches" (to see them do `git branch -a`). To get rid of these do `git fetch --all --prune`.
    (I still don't know what the pune option does, must look into it.)
