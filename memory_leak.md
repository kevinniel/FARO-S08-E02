# En cas de problème de fuite mémoire

- Si vous rencontrez des problèmes de fuite de mémoire à cause des sessions, utilisez le module memorystore pour définir une expiration des sessions : memorystore (https://www.npmjs.com/package/memorystore)
- `npm i memorystore`
- `nano app.js`
- voir les modifs à apporter ci-dessous
- Note : Pour des environnements de production où les sessions doivent persister au redémarrage du serveur, envisagez de stocker les sessions dans une base de données avec session-sequelize ou un autre module adapté.

## Fichier à modifier srx/app.js

```
import express from "express";
import router from "./routes/index.js";
import session from "express-session";
import createMemoryStore from "memorystore";
const app = express();

const MemoryStore = createMemoryStore(session);

// je configure le moteur de rendu
app.set("view engine", "ejs");
app.set("views", `${import.meta.dirname}/views`);

// je configure les sessions
app.use(
    session({
        secret: ["php master race"], // Clé secrète pour signer la session, utilisez une chaîne complexe et sécurisée
        resave: false, // Force la session à être sauvegardée dans la store, même si elle n'a pas été modifiée
        saveUninitialized: false, // Ne sauvegarde pas de session non initialisée
        store: new MemoryStore({
            checkPeriod: 86400000, // prune expired entries every 24h
        }),
        cookie: {
            maxAge: 86400000,
            secure: false, // Définit le cookie comme sécurisé, utilisez true en production avec HTTPS
            httpOnly: true, // Empêche l'accès au cookie via JavaScript côté client
        },
    })
);
// Body parser pour traiter les body au format des formulaires HTMP (`applicaiton/x-www-urlencoded`)
app.use(express.urlencoded({ extended: true }));

// je configure le dossier public
app.use(express.static(`${import.meta.dirname}/../public`));
// je configure les routes
app.use(router);

export default app;
```
