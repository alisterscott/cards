# The Conversation Deck

An MIT-licensed, mobile-first collection of 80 original open-ended conversation prompts for work socials. No accounts, backend or external dependencies.

## Publish to GitHub Pages

1. Unzip this archive. Copy **all contents**, including the hidden `.github` directory, into the root of [alisterscott/cards](https://github.com/alisterscott/cards) on the `main` branch.
2. In the repository, open **Settings → Pages**. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. Open **Actions** and check the **Deploy conversation cards to GitHub Pages** workflow, which also runs on every push to `main`.
4. Visit https://alisterscott.github.io/cards/ after deployment succeeds.

If uploading through the GitHub web interface, ensure `.github/workflows/deploy.yml` is included: hidden folders can be easy to miss. You can also use Git locally:

```sh
git clone https://github.com/alisterscott/cards.git
cd cards
# Copy the unzipped files into this directory, including .github
 git add .
 git commit -m "Add conversation deck website"
 git push origin main
```

## How it works

- Use **All cards** or a category filter. Each filter has its **own independently shuffled deck**, saved in localStorage on that browser. No question repeats **within that filter's cycle** before all its cards have appeared. Since category decks and the All deck are independent, switching filters can show a question you have already seen in another filter.
- Closing and reopening the site retains the current question and shuffle, provided browser storage is available. Private browsing, clearing site data or a different device will start fresh.
- After the last card in a filter, the next tap reshuffles that filter and starts a new cycle.
- **Share site** opens a modal with a pre-generated QR code for the production URL; **Share card** copies a link using the `?card=` parameter (or opens the device share sheet).
- Card changes in `cards.json` are reconciled with existing saved queues, so additions/removals do not cause failures.
- This is a static site; all data stays on the device. No tracking or analytics.

## Editing questions

Edit `cards.json`. Keep each `id` unique and categories as `ice`, `imagine`, `big`, `ethics`. Changes publish after you commit and push. The QR code in `assets/qr.png` points to the published URL; regenerate it if the domain changes.

## License

[MIT](LICENSE), including the original prompts in `cards.json`.
