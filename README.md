<div align="center">

![wakatime-charts](https://socialify.git.ci/dvjn/wakatime-charts/image?description=1&font=Inter&owner=1&pattern=Charlie%20Brown&theme=Light "wakatime charts")

![GitHub Repo stars](https://img.shields.io/github/stars/dvjn/wakatime-charts?color=%23dfb317&style=for-the-badge "Github Repo stars")
![GitHub forks](https://img.shields.io/github/forks/dvjn/wakatime-charts?color=%2397ca00&style=for-the-badge "Github forks")
![GitHub pull requests](https://img.shields.io/github/issues-pr-raw/dvjn/wakatime-charts?color=%23fe7d37&label=PULLS&style=for-the-badge "Github pull requests")

---

![Weekly Language Stats](https://raw.githubusercontent.com/zo-ly/zo-ly/main/images/wakatime_weekly_language_stats.svg "Weekly Language Stats")
![Weekly Language Stats](https://raw.githubusercontent.com/zo-ly/zo-ly/main/images/wakatime_weekly_language_stats_dark.svg "Weekly Language Stats Dark")

</div>

## How to Use 🚀

### Set it up in your repository ⚙️

1. Add your wakatime api key from [here](https://wakatime.com/settings/api-key), in your repository secrets with the name `WAKATIME_API_KEY`.

2. **Optional:** If you are adding this action to a repository other than your profile repository (`<username>/<username>`), add your Github API Token from [here](https://github.com/settings/tokens), in your repository secrets with the name `GITHUB_TOKEN`.

3. Go to actions tab of your repository, click `New workflow`, and then click the link `set up a workflow yourself`.

4. Replace all the file contents with the following:

   ```yaml
   name: Wakatime Charts

   on:
     workflow_dispatch:
     schedule:
       - cron: "0 10 * * *"

   jobs:
     update-charts:
       name: Update wakatime stats charts
       runs-on: ubuntu-latest
       steps:
         - uses: zo-ly/wakatime-charts@master
           with:
             WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
             GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} # only required if using the action in repository other than profile
   ```

5. Commit this workflow file.

**Note:** The action will run at 00:00 UTC everyday to update the images.

### Other Parameters 🔧

- `BRANCH_NAME`: Set the branch on which charts are pushed. Defaults to `master`
- `COMMIT_MESSAGE`: Set the commit message for the changes. Defaults to `📊`
- `IMAGES_FOLDER`: Set the folder name in which generated images are stored. Defaults to `images`
- `GIT_USER_EMAIL`: Set the user email for git config. Defaults to Github Action Bot's email `41898282+github-actions[bot]@users.noreply.github.com`
- `GIT_USER_NAME`: Set the user name for git config. Defaults to `Github Action`

### Using generated images 🔗

Link for the generated images is:
`https://raw.githubusercontent.com/<username>/<repository>/<branch_name>/<images_folder>/<chart_name>.svg`

Where, the chart name is one of `wakatime_weekly_language_stats` and `wakatime_weekly_language_stats_dark` .

## Inspiration 😍

- [wakatime-readme](https://github.com/marketplace/actions/waka-readme)
- [Profile-Readme-WakaTime](https://github.com/marketplace/actions/wakatime-stat-update-action)
- [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
