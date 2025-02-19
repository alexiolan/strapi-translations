# 🌍 Strapi Admin Panel Localization

This repository contains localization settings for the **Strapi Admin Panel**, allowing you to support multiple languages in the admin interface.

## 🛠️ Installation

Ensure that your Strapi project is set up and that you have the required translation file placed inside the `/src/translations` directory.

## 📂 Project Structure

```
📂 my-strapi-project
 ├── 📂 src
 │    ├── 📂 admin
 │    │    ├── app.tsx
 │    ├── 📂 translations
 │    │    ├── en.json
 │    │    ├── ru.json
 ├── package.json
```

## 📜 Configuration

The translation setup is defined in the `` file inside the **admin** panel directory.

### Example: `app.tsx`

```tsx
import type { StrapiApp } from '@strapi/strapi/admin';
import ru from '../translations/ru.json';

export default {
  config: {
    locales: [
      'ru'
    ],
    translations: {
      ru: {
        ...ru
      },
    },
    languageNativeNames: {
      ru: 'Русский',
    },
  },
  bootstrap(app: StrapiApp) {
    console.log(app);
  },
};
```

### Explanation:

- ``: Defines available languages (e.g., `'ru'` for Russian).
- ``: Imports the JSON file containing translations.
- ``: Specifies how the language name appears in the UI.

## 🗂️ Translation File Format

Each language file (e.g., `ru.json`) should follow the JSON format:

```json
{
  "app.title": "Панель администратора",
  "app.welcome": "Добро пожаловать в Strapi"
}
```

## 🌍 Switching Languages

To change the language in the Strapi admin panel:

1. Go to **User Profile Settings** in the Strapi admin.
2. Select the desired language from the **Available Languages** list.
3. Save and refresh the page.

## ✅ Additional Notes

- Ensure the translation JSON file follows the correct format.
- Restart Strapi after adding new translations.
- More languages can be added by updating `app.tsx` and adding corresponding JSON files.

