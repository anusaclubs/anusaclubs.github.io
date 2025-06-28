### ANUSA Clubs and Societies Resources Portal

The ANUSA Clubs and Societies Resources Portal is the central source of truth for running a club at the ANU. Its goal is to be a one-stop-shop for club executives, containing all the guides, forms, templates, and key information needed to manage a club successfully.

The portal is a living document, maintained by the ANUSA Clubs Team with the help of community contributors like you. By keeping it up-to-date, we ensure that every club has access to the best possible information.


## Contributing
There are three main ways you can contribute:

1.  **The Easy Way:** Making quick edits directly on GitHub.
2.  **The Advanced Way:** For larger changes using the full Git workflow.
3.  **Via Email:** For those who prefer not to use GitHub.

---

### Method 1: The Easy Way (Quick Edits on GitHub)

This method is perfect for simple content changes, like fixing typos, updating links, or rewriting a paragraph. It all happens in your web browser.

1.  **Find the page:** Navigate to the page you want to edit on the [ANUSA Clubs and Societies Resources Portal website](https://anusaclubs.github.io/).
2.  **Go to the GitHub file:** You can find the corresponding file in the [GitHub repository](https://github.com/anusaclubs/anusaclubs.github.io). The files for the website pages are located in [docs](https://github.com/anusaclubs/anusaclubs.github.io/tree/main/docs).
3.  **Click the pencil icon:** In the top right corner of the file view on GitHub, you'll see a pencil icon with the tooltip "Edit this file". Click it.
4.  **Make your changes:** An in-browser text editor will open. Make the changes you want to the text.
5.  **Propose the change:** Once you're done, scroll to the bottom of the page.
    *   In the first box, write a short, clear summary of your change (e.g., "Fix broken link on the events page").
    *   You can add more detail in the larger description box below if needed.
6.  **Click "Propose changes":** This will automatically create a "pull request" for the project maintainers to review. They will be notified of your suggestion and can merge it into the live site.

---

### Method 2: The Advanced Way (For Larger Changes)

This method is best if you want to add new documents, work on structural changes, or preview your changes on your own computer before submitting them. It follows the standard "fork and pull request" workflow.

#### Getting Started
1.  **Fork the Repository:** Click the "Fork" button on the top-right of the [repository page](https://github.com/anusaclubs/anusaclubs.github.io). This creates your own copy of the project.
2.  **Clone Your Fork:** On your computer, run the following command in your terminal (replace `YOUR-USERNAME` with your GitHub username):
    ```bash
    git clone https://github.com/YOUR-USERNAME/anusaclubs.github.io.git
    ```
3.  **Navigate to the Directory:**
    ```bash
    cd anusaclubs.github.io
    ```

#### Making a Contribution
1.  **Create a New Branch:** Always work on a new branch to keep your changes organized.
    ```bash
    git checkout -b your-branch-name
    ```2.  **Make Your Edits:** Use your favorite code editor to make changes or add new files.
3.  **(Optional) Preview Your Changes:** This website is built with Jekyll. To see what your changes will look like, you can run a local server. You'll need to have Ruby and Jekyll installed. Full instructions can be found on the [Jekyll website](https://jekyllrb.com/docs/installation/). Once installed, you can usually preview the site by running `bundle exec jekyll serve` in the project directory.
4.  **Commit Your Changes:** Save a snapshot of your work.
    ```bash
    git add .
    git commit -m "A brief description of your changes"
    ```
5.  **Push to Your Fork:**
    ```bash
    git push origin your-branch-name
    ```
6.  **Create a Pull Request:** Go to your fork on GitHub. You will see a prompt to "Compare & pull request". Click it, review your changes, and submit the pull request for the maintainers to review.

---

### Method 3: Contribute via Email

If you're not comfortable with GitHub, we are more than happy to make the changes for you.

1.  **Draft an Email:** Open your email client and compose a message to **sa.clubsofficer@anu.edu.au**.
2.  **Use a Clear Subject Line:** For example, "Contribution Suggestion for Resources Portal".
3.  **Describe Your Change:** In the body of the email, please include:
    *   **The Page:** The full URL of the page you want to see changed.
    *   **The Change:** Clearly explain what needs to be updated, added, or removed. It's helpful if you copy and paste the text you want to change and provide the new text.
    *   **New Resources:** If you are submitting a new resource (like a guide or template), please attach it to the email, preferably in a format like Microsoft Word or a plain text file.

The Clubs Team will review your suggestion and upload it to the portal.

---

### A Note on Contributors

This portal is built by and for the ANU clubs community. We deeply appreciate every contribution, from fixing a single typo to writing a whole new guide.

To acknowledge your effort, we maintain a list of everyone who has helped improve this resource. When your contribution (via a pull request or email) is accepted, we will add your name and a link to your LinkedIn or Github (if applicable) to our contributors' page. Thank you for helping us make this the best resource it can be!

### Questions?

If you have any questions about contributing or the portal itself, please don't hesitate to email us at **sa.clubsofficer@anu.edu.au**.