# SpendWise: Budget Tracker Dashboard

## Project Description

SpendWise is a responsive budgeting dashboard that helps a user see where their money goes each month. The user sets a monthly budget, records expenses under categories (Food, Transport, Rent, Entertainment, Savings and Utilities), and the dashboard instantly shows how much has been spent, how much is left, and which categories are close to or over their limits.

**What the app does**

- Shows the total spent against the monthly budget, the remaining balance and the percentage of the budget used.
- Displays one card per category with a progress bar that changes colour as the limit gets close (green, then gold, then red).
- Lets the user add expenses with a description, category, amount and date, with validation and friendly error messages.
- Lets the user delete an expense, filter the expense list by category, change the monthly budget, restore the sample data, or clear everything.
- Saves the data in the browser (`localStorage`), so expenses are still there after a refresh.
- Adapts to screen size (single column below 768px) and to the user's light or dark colour scheme.

**JavaScript concepts used**

- Variables (`const`, `let`) and data types: numbers, strings, booleans, arrays and objects.
- Arrays of objects for categories and expenses, with `filter()`, `map()` and `sort()`.
- Loops (`for...of`, `for...in`) to total spending and build the page.
- Conditionals (`if / else if / else`) for input validation and budget status messages.
- Reusable functions that each do one job (for example `calculateTotalSpent`, `calculateRemaining`, `calculatePercentUsed`, `formatCurrency`).
- DOM manipulation and event listeners (`submit`, `click`, `change`), including event delegation for the delete buttons.
- `localStorage` with `JSON.stringify` and `JSON.parse` to keep data between visits.

## Technologies Used

- **HTML5** with semantic elements (`aside`, `header`, `main`, `section`, `article`) and ARIA attributes for accessibility
- **CSS3**: Grid, Flexbox, custom properties (CSS variables), a dark theme using `prefers-color-scheme`, media queries and reduced-motion support
- **JavaScript (ES6+)**: no frameworks or libraries
- **Google Fonts**: Inter and Poppins
- **Git and GitHub**: version control and source hosting
- **Netlify**: hosting and continuous deployment

## Live Netlify Website URL

**https://spendwise-robert.netlify.app**

## GitHub Repository Information

- **Repository URL:** `https://github.com/<your-github-username>/<your-repository-name>`  (replace with your real link)
- **Visibility:** Public
- **Branch deployed:** `main`

**Project structure**

```
spendwise/
├── index.html           Page structure
├── style.css            All styling (theme, layout, components, responsive rules)
├── script.js            Application logic
├── Spendwise_Logo.png   Logo shown in the sidebar
└── README.md            Project documentation
```

All files sit in the root of the repository, and every path in `index.html` is a simple relative path (for example `style.css`, `script.js`, `Spendwise_Logo.png`), so the site works the same locally and online.

## Deployment Process Summary

1. **Checked deployment readiness.** I confirmed the project is a static site with no build step, that `index.html` is in the root folder, and that the file names used in the HTML match the real file names exactly, including capital letters.
2. **Created a public GitHub repository** and uploaded the project files (`index.html`, `style.css`, `script.js`, `Spendwise_Logo.png` and this README).
3. **Connected the repository to Netlify** using *Add new site → Import an existing project → GitHub*, and chose the repository.
4. **Set the build settings:** no build command, and the publish directory set to the repository root, then clicked *Deploy*.
5. **Renamed the site** under *Site configuration → Change site name* from the random default to `spendwise-robert`, which gives the address above.
6. **Tested continuous deployment.** I made a visible change to the app: `[describe the change you made, for example "added a footer with the live site link"]`. I committed and pushed it to GitHub, and Netlify detected the push and redeployed automatically, so the live site showed the change without any manual upload.
7. **Tested the live site** on a laptop and on a mobile phone, checking that the page, styles, script, logo and fonts all load, and that adding, deleting and filtering expenses and updating the budget all work.

## Challenges Encountered During Deployment

- **Exact file names matter.** Downloaded copies of my files were renamed by the browser (for example `style (1).css` and files with extra letters added). The HTML links to `style.css`, `script.js` and `Spendwise_Logo.png`, so a differently named file makes the page load unstyled or without its script. Netlify's servers are also case-sensitive, so `Spendwise_Logo.png` and `spendwise_logo.png` are different files.
- **Spaces in file names.** An earlier version of the project used a logo called `Spendwise Logo.png`. Spaces in file names are awkward in URLs, so I renamed it to `Spendwise_Logo.png`.
- **Browser storage is per device.** The app saves data with `localStorage`, which is stored separately in each browser. Expenses added on my laptop do not appear on my phone, and each device starts from the sample data. This is expected for a front-end-only app, but it was surprising when I tested on two devices.
- **Testing the live site, not just my computer.** Something that works from a local file can still fail online if a path is wrong, so I tested the deployed address itself rather than relying on local testing.

## Lessons Learned

- A static site is the simplest thing to deploy: no build command is needed, and Netlify only needs the repository and the folder to publish.
- Continuous deployment saves a lot of time. Pushing to GitHub is enough to update the live website, and Netlify keeps a history of deploys that can be rolled back if something breaks.
- Keeping file names simple (lowercase, no spaces, matching the HTML exactly) prevents most "it works on my computer" problems.
- Always test the live URL on more than one device, because screen sizes and browser storage differ.
- A clear README, with the live link and a short deployment summary, makes a project much easier for other people to understand and review.

## Author

Robert Wamalwa Wanjala
