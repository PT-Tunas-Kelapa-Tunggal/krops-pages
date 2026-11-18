# Krops public pages

Static Indonesian support and privacy pages for Krops, maintained by Krops Development Team. Public contact: **contact@krops.tech**.

No framework, package installation, JavaScript, backend or build step is required. All assets are local and all internal links are relative so the site works under a GitHub Pages repository path.

## Files

- `index.html` — landing page linking to support and privacy.
- `support/index.html` — support contact, troubleshooting and data-request instructions.
- `privacy/index.html` — privacy policy.
- `assets/site.css` — shared responsive styles.
- `assets/krops-mark.png` — existing Krops mark from the iOS project.
- `.nojekyll` — serve the static files directly.

## Before publishing

- The policy reflects the team's stated practice: process only service-related data, do not sell data, and allow deletion after the service. Review section 5 before publication: the current app does not delete CloudKit records through its garden-delete action, so self-service server deletion must be implemented and verified before it is promised. Confirm the manual request process or update it to the verified self-service flow, then remove the draft notice and the remaining `REVIEW BEFORE PUBLISHING` comment.
- Confirm that the policy describes the actual released app and the team's operational practices, including CloudKit access and sharing with assessment staff.
- Confirm that contact@krops.tech is monitored for support, correction and deletion requests.
- The current app does not delete submitted CloudKit records when a garden is removed from the app. Handle verified server-data deletion requests through the team's confirmed process.
- Recheck the date on the policy when publishing or changing its substance.

## App Store privacy declaration

Service-only use, no data sale, and deletion after the service do not make stored CloudKit submissions “Data Not Collected” under Apple's definition. Declare the data actually transmitted and retained for the assessment under **App Functionality**, and answer tracking questions according to the app's actual practices. Contact details and precise farm coordinates are included in the current submission payload. Data processed only on-device can be assessed separately. See [Apple's data-collection guidance](https://developer.apple.com/app-store/app-privacy-details/).

## Publish with GitHub Pages

1. Create a GitHub repository named `krops-pages`. Use a public repository for GitHub Free.
2. Commit and push the **contents of this folder at the repository root**, so GitHub shows `index.html`, `support/` and `privacy/` at the top level.
3. Open the repository's **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Choose the branch containing these files (usually `main`) and the folder **/(root)**, then click **Save**.
6. Wait for the Pages deployment to finish. The **Actions** tab shows the deployment status; **Settings → Pages** shows the public site address and a **Visit site** link.
7. Confirm HTTPS is enabled in Pages settings. The default `github.io` domain supports HTTPS; a custom domain is optional.
8. Open both public pages in a signed-out/private browser window to confirm that the text, links, logo and stylesheet load without a sign-in.

No commit, push, repository creation or deployment has been performed by Codex.

## URLs for App Store Connect

For a GitHub owner named `YOUR-OWNER` and repository named `krops-pages`, the expected URLs are:

| App Store Connect field | Public URL |
| --- | --- |
| **M09 — Support URL**, under version 1.0 | `https://YOUR-OWNER.github.io/krops-pages/support/` |
| **M12 — Privacy Policy URL**, under App Privacy | `https://YOUR-OWNER.github.io/krops-pages/privacy/` |
| Optional Marketing URL | `https://YOUR-OWNER.github.io/krops-pages/` |

Replace the example owner/repository with the address displayed by **Settings → Pages**. A user/organization site or a custom domain will have a different base address; use the displayed base plus `support/` and `privacy/`.

Link the same public privacy URL inside the iOS app. Publishing this website does not add that in-app link or complete the App Privacy data-collection questionnaire.

## Updating the pages

Edit the relevant HTML, commit and push to the publishing branch. GitHub Pages redeploys the updated files. Keep page paths stable so submitted App Store URLs continue to work.

## Local preview

From this folder, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open `http://127.0.0.1:8000/`, `/support/` and `/privacy/`. Stop with Ctrl+C. This local server is only for preview; GitHub Pages hosts the public pages.

## References

- [GitHub Pages publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Pages and HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
- [Apple Support URL requirements](https://developer.apple.com/help/app-store-connect/reference/app-information/platform-version-information/)
- [Apple privacy policy requirements](https://developer.apple.com/app-store/review/guidelines/#privacy)
- [GitHub Pages hosting and security logs](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)
