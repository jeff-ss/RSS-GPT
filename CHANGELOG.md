# CHANGELOG

- 2023-09-20:
  - GitHub Pages destination url is no longer needed to be set manually in `main.py`. Instead, the script directly get the username from repo secrets and concatenate it to `https://username.github.io/repo_name/`. You will still need to manually change the repo name used in the script if you forked this repo and renamed it.
  - Removed the GitHub work deploy GitHub pages but instead using deployment from a certain branch, because the GitHub workflow deployment is not working properly for some reason. It could be because of the deployment branch is not the default branch.

- 2023-09-19:
  - I have created a new branch and put all auto commits in that branch. You can check it out [here](https://github.com/yinan-c/RSS-GPT/tree/auto-commit). The main branch will only contain manual commits from now on, so that you can easily check out the changes of the script and merge it to your repo.
  - Updated the GitHub Pages destination url from `./_site/rss/` to `./_site/` in the workflow file. The feeds are now hosted in the `your_path/RSS-GPT` instead of the `rss/` subdirectory. Updated the feeds links in README.

- 2023-09-15:
  - Now if you don't have an OPENAI API, you can still use the script to aggregate and filter your RSS feeds, but without the summarization feature. (You can do this by removing or setting a random string in the OPENAI_API_KEY secret in your repo setting. Alternatively, you can just set `max_items=0` or remove `max_items` in config.ini)

  - Also, whenever there is a problem with OPENAI API calling, the script will still run and fetch new articles from the RSS feeds, just without AI summaries.

  - When you find your feeds does not contain summaries, you can check the log in rss/ directory to see if there is any error message from OPENAI, common problems include billing issues etc.