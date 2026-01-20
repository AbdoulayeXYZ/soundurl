# Sound URL - Notifications Audio Wialon

Système de déclenchement automatique de sons via URL pour les notifications Wialon.

## 🏗️ Architecture

```
soundurl/
├── index.html          # Page d'accueil avec liste des sons
├── play.html           # Lecteur dynamique unique
├── library/            # Bibliothèque de sons
│   ├── buzzer.mp3
│   └── notification.mp3
└── README.md
```

## 🎯 Utilisation

### URLs disponibles

Chaque son est accessible via un paramètre URL :

- **Buzzer** : `play.html?sound=buzzer`
- **Notification** : `play.html?sound=notification`

### Exemple d'utilisation

```
https://votre-domaine.com/play.html?sound=buzzer
```

Le son se déclenche automatiquement à l'ouverture de l'URL.

## ➕ Ajouter un nouveau son

1. **Ajouter le fichier audio** dans le dossier `library/`
   ```bash
   cp mon-son.mp3 library/
   ```

2. **Configurer le son** dans `play.html`
   
   Ajouter une entrée dans l'objet `soundConfig` :
   ```javascript
   const soundConfig = {
       // ... sons existants
       monson: {
           file: 'library/mon-son.mp3',
           name: 'Mon Son',
           icon: '🎵',
           gradient: 'linear-gradient(135deg, #FA8BFF 0%, #2BD2FF 100%)',
           description: 'Description de mon son'
       }
   };
   ```

3. **Ajouter le lien** dans `index.html`
   ```html
   <a href="play.html?sound=monson" class="sound-card">
       <div class="sound-icon">🎵</div>
       <div class="sound-info">
           <div class="sound-name">Mon Son</div>
           <div class="sound-desc">Description de mon son</div>
       </div>
       <div class="arrow">→</div>
   </a>
   ```

4. **Accéder au son** : `play.html?sound=monson`

## 🚀 Déploiement

### Option 1 : Vercel
```bash
vercel deploy
```

### Option 2 : Netlify
```bash
netlify deploy
```

### Option 3 : GitHub Pages
1. Push sur GitHub
2. Activer GitHub Pages dans les settings du repo
3. Accéder via `https://username.github.io/soundurl/`

## 📝 Notes

- Les navigateurs modernes peuvent bloquer l'autoplay. Un bouton de secours apparaît automatiquement.
- Tous les sons sont en format MP3 pour une compatibilité maximale.
- Le design est responsive et fonctionne sur mobile et desktop.

## 🎨 Personnalisation

Chaque son peut avoir :
- **Icône** : Emoji personnalisé
- **Gradient** : Couleur de fond unique
- **Description** : Texte descriptif
- **Nom** : Titre affiché

## 📄 Licence

Projet personnel pour notifications Wialon.
