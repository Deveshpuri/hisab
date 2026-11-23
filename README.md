# Hisab: Devesh & Vishal

Free shared expense tracker. Static site on GitHub Pages, data in Firebase Firestore, no login. Privacy comes from a secret key in the link's `#` part (never stored in this repo).

## Go live (one time)
1. **Firebase**: console.firebase.google.com > Add project > Build > Firestore Database > Create (production mode).
2. Project settings > Your apps > Web (`</>`) > copy the config into `firebase-config.js` (apiKey, authDomain, projectId, appId).
3. Firestore > Rules > paste `firestore.rules` > Publish.
4. **GitHub Pages**: repo Settings > Pages > Deploy from branch `main` / root.
5. Open `https://deveshpuri.github.io/hisab/`, tap **Create new hisab**, then **Share** the private link with Vishal only.

Without a Firebase config the app runs in local demo mode (data stays on that device).

## Notes
- Entries are soft-deleted; every add/edit/delete is written to an append-only log.
- Balance maths: positive = Vishal owes Devesh. Expense: payer D adds `a*(1-dShare)`, payer V subtracts `a*dShare`; loan/repayment by D adds `a`, by V subtracts `a`.
- PDF: tap **PDF** then choose "Save as PDF" in the print dialog.
- Lost or leaked link? Create a new hisab and re-enter, or ask to migrate the data to a new key.
