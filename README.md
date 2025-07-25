📁 Détail et explication des dossiers/fichiers

1. tests/
   ➡️ Contient tous les scénarios de test Playwright
   Fichiers .spec.js = chaque fichier teste un cas ou une fonctionnalité (E2E, UI, etc.)

Exemple Description
login.spec.js Test du formulaire de connexion Salesforce
dashboard.spec.js Vérifie l’accès au dashboard et ses composants
profile.spec.js Teste la mise à jour du profil utilisateur

2. pages/
   ➡️ Implémente le modèle Page Object Model (POM)
   Chaque fichier représente une page de l’application, avec ses sélecteurs et ses fonctions.

Exemple Contenu
LoginPage.js Méthodes : fillUsername(), clickLogin(), isErrorVisible()
DashboardPage.js Méthodes : navigateToProfile(), getWelcomeMessage()

📌 Avantage : rend tes tests réutilisables et maintenables.

3. utils/
   ➡️ Dossier pour les fonctions utilitaires, constantes ou helpers

Fichier Contenu
helpers.js Ex. : waitForElement(), generateRandomEmail()
constants.js URLs de base, mots de passe tests, sélecteurs globaux, etc.

4. config/
   ➡️ Contient la configuration principale de Playwright

Fichier Utilité
playwright.config.js Définit les navigateurs à tester, les délais, les retries, la baseURL, les rapports, etc.

Exemple :

js
Copy
Edit
const { defineConfig } = require('@playwright/test');

module.exports = defineConfig({
timeout: 30000,
use: {
baseURL: 'https://login.salesforce.com',
headless: true,
viewport: { width: 1280, height: 720 },
screenshot: 'only-on-failure',
},
reporter: [['html', { open: 'never' }]],
}); 5. reports/
➡️ Dossier généré automatiquement après les tests (via HTML reporter, Allure, etc.)

Tu y trouveras les résultats de test, logs, captures d’écran

Tu peux ouvrir index.html pour voir les résultats graphiquement

6. .env
   ➡️ Stocke les informations sensibles (mots de passe, tokens...)

Exemple :

ini
Copy
Edit
ADMIN_USERNAME=admin@test.com
ADMIN_PASSWORD=secret123
Puis tu y accèdes dans les tests via process.env.ADMIN_USERNAME

7. package.json
   ➡️ Fichier de configuration du projet Node.js

Il contient :

les dépendances (ex: @playwright/test)

les scripts (ex: npm test, npm run report)

les infos du projet

8. README.md
   ➡️ Documentation rapide pour ton projet (setup, commandes, structure...)

9. node_modules/
   ➡️ Dossier créé automatiquement par npm install
   Contient toutes les bibliothèques (Playwright, etc.)

🚀 Commandes utiles
Commande Action
npm init -y Créer package.json
npm install -D @playwright/test Installer Playwright
npx playwright install Installer les navigateurs (Chromium, Firefox...)
npx playwright test Lancer tous les tests
npx playwright show-report Voir le rapport HTML
#   S t a g e  
 