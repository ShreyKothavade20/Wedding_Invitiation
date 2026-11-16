# Shrey & Subhrima — GitHub Pages wedding website

This version was adapted from your uploaded `Index(4).html` and runs as a STATIC website on GitHub Pages.

## What's changed
1. Celebrations + venue now share a single page/tab.
2. Madhav Banquet (near Seawoods, actually listed in Nerul East, Sector 19A) has a working Google Maps link on the venue and celebration cards.
3. The old on-page RSVP form (built for Google Apps Script) was removed. The RSVP tab has a button to open your Google Form **after you add its respondent URL**.
4. Two photo slots: cover background on page 1 and a portrait on the Our Story page. Optional story gallery.
5. All ceremony dates stay **unconfirmed** because the brief contained conflicting dates. No backend or Sheets credentials are exposed.

## Upload on GitHub (replace your previous site)
- Put `index.html` at the **root** of the repository. On GitHub choose `Add file` > `Upload files`, then `Commit changes`. Delete/replace older `Index.html` or `index (1).html` if necessary.
- Keep the `photos` folder beside `index.html`. It is OK if you don't have photos yet.
- Verify under Settings > Pages that Source = `Deploy from a branch`, Branch = `main`, Folder = `/(root)`.
- Open Actions > `Pages build and deployment` and wait for a green tick, then open Settings > Pages > `Visit site`. Force refresh Ctrl + Shift + R.

## Add couple photos
1. In the GitHub repo, create folder `photos` if it does not exist.
2. Upload a landscape photo as `photos/cover.jpg` (cover photo displayed behind white text on Invitation). Recommended 1600x1000 or larger.
3. Upload a portrait or square couple photo as `photos/story.jpg` (Our Story). Recommended 1000x1200 or larger.
4. Commit. The site automatically detects them. No code edit needed for these two filenames.
5. For a gallery, upload `photos/gallery1.jpg` etc, then edit the config near the TOP of `index.html` to: `gallery: ["photos/gallery1.jpg", "photos/gallery2.jpg"]`.

## RSVP link — basic connector, no direct database yet
1. Open [Google Forms](https://forms.google.com/) and create/select the form to collect guest responses.
2. In the Form **Responses** tab, link to your **existing Google spreadsheet** using 'Select destination for responses' > 'Select existing spreadsheet'. Google Forms normally creates/uses a dedicated response sheet tab inside it; it does **not automatically update all your existing custom tables**.
3. Copy the **respondent** URL (typically `https://docs.google.com/forms/d/e/.../viewform`). Do not publish the Google Sheet editing URL.
4. Edit `index.html` near the beginning and paste the link:
   `rsvpFormUrl: "https://docs.google.com/forms/d/e/YOUR_FORM_ID/viewform",`
5. Commit. The RSVP page button will become clickable and open Google Forms in a new tab.
6. To map responses across your custom tables later, we can add Apps Script once you provide the form fields and sheet structure. The current site does **not save RSVP responses directly**.

## Edit venue
The verified location is near Haware Mall, Sector 19A, Nerul East, Navi Mumbai. You described it as Seawoods; the public listing calls it **Nerul East, near Seawoods**.
Current Google Maps URL:
https://www.google.com/maps/search/?api=1&query=Jagatguru+Aadi+Shankracharya+Marg%2C+near+Haware+Mall%2C+Sector+19A%2C+Nerul+East%2C+Navi+Mumbai%2C+Maharashtra+400706

## Publish updates
Each time you edit or upload files, select **Commit changes**. Visit GitHub > Actions for deployment status and refresh the live Pages URL after success.
