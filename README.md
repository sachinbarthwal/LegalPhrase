# Legal Phrase Explainer

A simple, interactive tool that explains legal phrases in plain English — with usage examples — useful for non-lawyers or new users creating legal documents.

## 🚀 Live Demo

[Legal Phrase Explainer on GitHub Pages](https://sachinbarthwal.github.io/LegalPhrase/)

## ✨ Features

- **Search Input (Autocomplete):** Find legal terms as you type.
- **Result Card:** See plain English explanations and example usage.
- **Category Tags:** Terms are grouped by contract type (e.g., NDA, Contract).
- **Responsive UI:** Works on desktop and mobile.

## 🛠️ Tech Stack

- **Frontend:** Vue 3 (Composition API)
- **Styling:** Custom CSS (no Tailwind)
- **Data:** Static local JSON file
- **Hosting:** GitHub Pages

## 📦 Local Development

1. **Clone the repo:**
   ```bash
   git clone https://github.com/sachinbarthwal/LegalPhrase.git
   cd LegalPhrase
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run the app locally:**
   ```bash
   npm run dev
   ```

4. **Build for production:**
   ```bash
   npm run build
   ```

## 📁 Project Structure

```
LegalPhrase/
├── src/
│   ├── components/
│   │   ├── SearchBar.vue
│   │   └── ResultCard.vue
│   ├── data/
│   │   └── terms.json
│   ├── App.vue
│   ├── main.js
│   └── assets/
│       └── main.css
├── index.html
├── package.json
├── vite.config.js
└── .github/
    └── workflows/
        └── deploy.yml
```

## 📝 License

MIT