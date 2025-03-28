---
title: Upgrade the Streamlit version of your app on Streamlit Cloud
slug: /knowledge-base/deploy/upgrade-streamlit-version-on-streamlit-cloud
---

# Upgrade the Streamlit version of your app on Streamlit Cloud

Want to use a cool new Streamlit feature but your app on Streamlit Cloud is running an old version of the Streamlit library? If that's you, don't worry! All you need to do is upgrade your app's Streamlit version. Here are five ways to do this, based on how your [app manages dependencies](/streamlit-cloud/get-started/deploy-an-app/app-dependencies):

## No dependency file

#### Reboot the app

1. Visit the app on Streamlit Cloud.
2. Click on the **Manage app** field in the bottom right (while logged in).
3. Go into the three-dot dropdown menu, and click on **Reboot app**.
4. After a few minutes, your app should come back running the newest version of the Streamlit library.

## `requirements.txt`

1. If the Streamlit version is not pinned (i.e., the requirements file contains a line with `streamlit` and nothing else):
   - Reboot the app as described above.
2. If the Streamlit version is pinned (e.g., `streamlit==1.0.0`):
   - Adapt the pinned version in the requirements file and push it to GitHub.
   - The app on Streamlit Cloud will reboot automatically as soon as it detects these changes.

## pipenv/poetry/conda

If you use any of these dependency managers, you probably know what you need to do. 😉

1. On your local computer, run the command to update the Streamlit package:
   - `pipenv update streamlit` or
   - `poetry update streamlit` or
   - With an activated conda environment, run:
     - `pip install -U streamlit` **and**
     - `conda env export`
2. Then push any changes to Pipfile.lock or poetry.lock or environment.yml to GitHub.
3. The app on Streamlit Cloud will reboot automatically as soon as it detects these changes.
