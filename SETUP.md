To implement the task management app with the specified technologies, follow these steps:

### 1. Setup Project

1. **Initialize Vite Project:**
   ```sh
   npm create vite@latest ./ --template react-ts
   ```

2. **Install Dependencies:**
   ```sh
   npm install @reduxjs/toolkit react-redux @mui/material @emotion/react @emotion/styled @mui/icons-material react react-dom react-router react-router-dom
   ```

3. **Install devDependencies:**
   ```sh
   npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-react eslint-plugin-react-hooks vite-plugin-eslint @types/react @types/react-dom @types/react-router @types/react-router-dom @types/node @eslint/js @vitejs/plugin-react eslint-plugin-react-refresh globals typescript vite
   ```

### 2. Configure Prettier

Create a `.prettierrc` file:
```json
{
   "singleQuote": true,
   "semi": true,
   "jsxBracketSameLine": false,
   "useTabs": false,
   "tabWidth": 4,
   "printWidth": 120,
   "bracketSpacing": false,
   "endOfLine": "crlf",
   "trailingComma": "all",
   "arrowParens": "always"
}
```

### 3. Configure Typescript

Replace the code in `tsconfig.app.json` with:
```json
{
   "compilerOptions": {
      "target": "ES2020",
      "useDefineForClassFields": true,
      "lib": ["ES2020", "DOM", "DOM.Iterable"],
      "module": "ESNext",
      "skipLibCheck": true,

      "moduleResolution": "bundler",
      "allowImportingTsExtensions": true,
      "isolatedModules": true,
      "moduleDetection": "force",
      "noEmit": true,
      "jsx": "react-jsx",

      "strict": true,
      "noUnusedLocals": true,
      "noUnusedParameters": true,
      "noFallthroughCasesInSwitch": true,
      "baseUrl": "./",
      "paths": {
         "@Layouts/*": ["src/Layouts/*"],
         "@Widgets/*": ["src/Widgets/*"],
         "@Pages/*": ["src/Pages/*"],
         "@Routes/*": ["src/Routes/*"],
         "@Store/*": ["src/Store/*"],
         "@Hooks/*": ["src/Hooks/*"],
         "@Providers/*": ["src/Providers/*"]
      }
   },
   "include": ["src"]
}
```

Replace the code in `tsconfig.node.json` with:
```json
{
   "compilerOptions": {
      "target": "ES2020",
      "useDefineForClassFields": true,
      "lib": [
         "ES2020",
         "DOM",
         "DOM.Iterable"
      ],
      "module": "ESNext",
      "skipLibCheck": true,
      "moduleResolution": "bundler",
      "allowImportingTsExtensions": true,
      "isolatedModules": true,
      "moduleDetection": "force",
      "noEmit": true,
      "jsx": "react-jsx",
      "strict": true,
      "noUnusedLocals": true,
      "noUnusedParameters": true,
      "noFallthroughCasesInSwitch": true,
      "baseUrl": "./",
      "paths": {
         "@/*": [
            "src/*"
         ]
      }
   },
   "include": [
      "vite.config.ts",
      "types"
   ]
}
```

### 4. Configure Vite

Replace the code in `vite.config.ts` with:
```ts
import {defineConfig} from 'vite';
import react from '@vitejs/plugin-react';
import eslintPlugin from 'vite-plugin-eslint';

export default defineConfig({
   plugins: [
      react(),
      eslintPlugin({
         include: ['/src/**/*.ts', '/src/**/*.tsx', '/src/**/*.js', '/src/**/*.jsx'],
      }),
   ],
   resolve: {
      alias: {
         '@Layouts': '/src/Layouts',
         '@Widgets': '/src/Widgets',
         '@Routes': '/src/Routes',
         '@Pages': '/src/Pages',
         '@Store': '/src/Store',
         '@Hooks': '/src/Hooks',
         '@Providers': '/src/Providers',
      },
   },
   server: {
      open: true,
   },
});
```

### 5. Create a `types` Folder

1. **Create the `types` folder in the root directory:**

   ```sh
   mkdir types
   ```

2. **Add the `vite-plugin-eslint` definition:**

   Create a file named `vite-plugin-eslint.d.ts` inside the `types` folder with the following content:

   ```typescript
   declare module 'vite-plugin-eslint';
   ```

This ensures that TypeScript recognizes the `vite-plugin-eslint` module.

### 6. Configure ESLint

Create or replace a `eslint.config.js` file in the root directory with the following content:

```js
import js from '@eslint/js';
import globals from 'globals';
import reactHooks from 'eslint-plugin-react-hooks';
import reactRefresh from 'eslint-plugin-react-refresh';
import tseslint from 'typescript-eslint';
import react from 'eslint-plugin-react';

export default tseslint.config(
    {ignores: ['dist']},
    {
        extends: [js.configs.recommended, ...tseslint.configs.recommended],
        files: ['**/*.{ts,tsx}'],
        languageOptions: {
            ecmaVersion: 2020,
            globals: globals.browser,
        },
        plugins: {
            'react-hooks': reactHooks,
            'react-refresh': reactRefresh,
            react,
        },
        rules: {
            ...reactHooks.configs.recommended.rules,
            'react-refresh/only-export-components': ['warn', {allowConstantExport: true}],
        },
    },
);
```