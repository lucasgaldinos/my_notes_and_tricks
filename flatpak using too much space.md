# Problem

After having disk usage limits fully occupied, I had to use "baobab - Disk usage analyzer" for where were the heavy files. Two folders have a lot of heavy items, /usr and /var.Inside /var, the folder flatpak/repo has some heavy objects and almost 8GB. I found one answer on internet for why: [stack overflow] and [linuxuprising]

before I gave you the link, now i want that [linuxuprising] take me to that link

## Solution

run:

`flatpak uninstall --unused`

After, the user can run the command:
`du -sh desired_folder`
Here -s is short for summarize, i.e. sum all the file size. -h is short for --human-readable

I didn't knew this command (I think it must come with gnu-core-utils and alsowith git-bash) and what it does is display the device usage by running through all files and spits their size in bytes. If -h is given, it'll recalculate for the most compressed size (12847632 becomes 13G)

##### Some cool aspects found on [linuxuprising]

flatpak has a mode where it install for a user only and not globally for the system.

[stack overflow]: https://stackoverflow.com/questions/56468429/cleanup-flatpak-repo-folder
[linuxuprising]: https://www.linuxuprising.com/2019/02/how-to-remove-unused-flatpak-runtimes.html
