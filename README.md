# Dev - Éditeur de Code
![Dev](https://img.shields.io/badge/version-1.3.0-blue) ![Platform](https://img.shields.io/badge/platform-Windows-blue)

![Dev Editor Logo](https://raw.githubusercontent.com/Sorabagu/Dev_HCE/refs/heads/screenshot/icon.png)

## 🖥️ À propos du logiciel

**Dev - Éditeur de Code** est un éditeur spécialement conçu pour travailler sur des projets HTML, CSS, et JavaScript. Ce logiciel met à disposition une interface moderne et ergonomique avec des fonctionnalités adaptées aux développeurs, tout en étant accessible gratuitement.

Ce projet a été développé dans un but **éducatif** pour permettre aux utilisateurs d'explorer des concepts de programmation, découvrir des pratiques modernes, et apprendre à construire des interfaces interactives.

---

## ✨ Fonctionnalités principales

- **Création et gestion de projets** : Sauvegardez et gérez vos projets au format `.devproj` pour une organisation simplifiée.
- **Prévisualisation en temps réel** : Visualisez vos modifications HTML, CSS, et JS instantanément grâce à une fenêtre dédiée.
- **Support de la responsivité** : Testez vos designs sur différentes tailles d'écrans (mobiles, tablettes, desktops).
- **Compatibilité étendue** : Importez ou exportez vos fichiers facilement pour collaborer ou partager vos projets.
- **Mode plein écran** : Travaillez sans distractions avec une prévisualisation plein écran.

---

## 🛠️ Ingéniosité dans les codes

### 1️⃣ **Gestion de la prévisualisation (Real-Time Update)**

Un des morceaux de code les plus ingénieux est la gestion dynamique des fichiers pour la prévisualisation. Cela permet de prendre en charge les modifications en temps réel avec `QWebEngineView` :

```python
def update_preview_from_content(self, html, css=None, js=None):
    """
    Met à jour la prévisualisation en générant un fichier temporaire.
    """
    preview_file = os.path.join(self.base_path, "temp_preview.html")
    content = f"""
    <!DOCTYPE html>
    <html>
    <head>
        <style>{css}</style>
    </head>
    <body>
        {html}
        <script>{js}</script>
    </body>
    </html>
    """
    with open(preview_file, "w", encoding="utf-8") as f:
        f.write(content)
    self.web_view.setUrl(QUrl.fromLocalFile(preview_file))
```

### 2️⃣ **Manifest dynamique**

Lors de la sauvegarde, un fichier `manifest.json` est généré pour organiser et répertorier tous les fichiers liés au projet. Cela simplifie l'importation et la gestion des ressources :

```python
def save_to_devproj(html_content, css_content, js_content, project_path):
    """
    Enregistre un projet et génère un manifest.json.
    """
    manifest_data = {
        "project_name": os.path.basename(project_path),
        "files": ["index.html", "styles.css", "script.js", "rsc/", "scripts/"],
    }
    with open(os.path.join(project_path, "manifest.json"), "w", encoding="utf-8") as f:
        json.dump(manifest_data, f, indent=4)
```

---

## 📝 But éducatif

Ce logiciel est avant tout un projet éducatif conçu pour :
- Comprendre la gestion d'une interface graphique complexe.
- Explorer les concepts de développement web et de gestion de projets.
- S'entraîner sur les langages `html`, `css` et `javascript`

Le logiciel est **totalement gratuit** et ouvert à toutes les suggestions.

---

## 📸 Captures d'écran

### **Interface principale**
![Interface principale](https://raw.githubusercontent.com/Sorabagu/Dev_HCE/refs/heads/screenshot/screenshot1.png)

### **Prévisualisation en temps réel**
![Prévisualisation](https://github.com/user-attachments/assets/a2114b49-dc48-4d97-ac58-5fc8c7b6d4f7)

---

## 🚀 Téléchargement

🔹 [setup_dev_1.3.0](https://github.com/Sorabagu/Dev_HCE/releases/download/Setup/setup_dev_v1.3.0.exe)

---

## 📧 Contact

Si vous souhaitez signaler un bug, demander une fonctionnalité ou simplement partager vos retours, n'hésitez pas à me contacter :

**Email :** [sora.dev.pro@gmail.com](mailto:sora.dev.pro@gmail.com)

Merci d'utiliser **Dev - Éditeur de Code** !

