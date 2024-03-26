# 🧪 EXPERIMENTAL 🧪

**This is a working proof-of-concept of a static Globus-powered research data portal.**

**⚠️ Until this notice is removed, usage of this repository is NOT recommended and is provided as-is.**

**We're looking forward to sharing more details about this repostiory and more at [GlobusWorld 2024](https://www.globusworld.org/)!**


----

<img src="https://github.com/globus/example-data-portal/assets/694253/29723bc0-d692-47d5-bdc3-2625d3712cf3" height="200px" alt="Globus + static" />

This is a static research data portal powered by Globus.

----

### Creating Your Own Static Research Data Portal

1. Create a new repository from the [globus/example-data-portal](https://github.com/globus/example-data-portal) template.
   * <img width="188" alt="Screenshot 2024-03-11 at 12 24 22 PM" src="https://github.com/globus/example-data-portal/assets/694253/abffa5a5-86c8-47d9-be4b-f249d34505ab">
1. [Update your repository to allow publishing with GitHub Actions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow).
1. [Ensure your GitHub Pages is configured to Enforce HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
1. Register an application on Globus – https://app.globus.org/settings/developers
   * You'll be creating an OAuth public client.
   * Update the **Redirects** to include your GitHub Pages URL + `/authenticate`, i.e., `https://globus.github.io/example-data-portal/authenticate`.
   * Optional: Specify the **Privacy Policy URL** and **Terms & Conditions URL** to the portal-provided routes, i.e. `https://globus.github.io/example-data-portal/privacy-policy`
1. Update the `static.json` to include:
   * `globus.application.client_id` – The UUID of the client created in **the previous step**.
   * `globus.transfer.collection_id` – The Collection UUID that will be the "source" of your data portal.
1. **That's it!** The changes made (and any future changes) to the `static.json` will trigger a GitHub Action that will automatically build and deploy your research data portal to your GitHub Pages URL.
