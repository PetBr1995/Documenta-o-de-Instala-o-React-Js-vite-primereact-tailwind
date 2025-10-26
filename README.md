# Documenta-o-de-Instala-o-React-Js-vite-primereact-tailwind

# 🟦 Projeto React + Vite + PrimeReact + PrimeFlex + Tailwind

Este projeto foi configurado do zero utilizando:

- **Vite** (ambiente de build rápido)
- **PrimeReact** (componentes UI)
- **PrimeIcons** (ícones)
- **PrimeFlex** (utilitários de layout)
- **TailwindCSS v3** (estilização utilitária)
- **PostCSS + Autoprefixer**

> A versão **v3 do Tailwind** foi utilizada para evitar problemas com o comando `npx tailwindcss init -p` no Windows.  
> Caso queira usar Tailwind v4+, veja a seção *"Usando Tailwind 4+"* ao final.

---

## 📦 Criação do Projeto com Vite

```bash
npm create vite@latest meu-projeto
cd meu-projeto
npm install

```
### Escolha a opção: React (JavaScript)

---
## 🌟 Instalação do PrimeReact

```
npm install primereact primeicons primeflex

```
- primereact → Componentes

- primeicons → Conjunto de ícones

- primeflex → Classes utilitárias (ex: flex, justify-content-center)

  #### Links para documentação primereact
  
  [Primereact](https://primereact.org/)
  [Primeflex](https://primeflex.org/)

  ---

  ## 🎨 Instalação do Tailwind (v3 recomendado)

  ### Remova qualquer versão anterior
  ```
    npm uninstall tailwindcss

  ```
  ### Instale 
  ```
  npm install -D tailwindcss@3 postcss autoprefixer
  npx tailwindcss init -p

  ```
  ### Serão gerados dois arquivos

  ```
  tailwind.config.js
  postcss.config.js
  ```
  ### ⚙️ Configuração do tailwind.config.js
  ```javascript
   /** @type {import('tailwindcss').Config} */
    export default {
    content: [
        "./index.html",
        "./src/**/*.{js,jsx,ts,tsx}"
      ],
      theme: {
        extend: {},
      },
      plugins: [],
    }

  ```
  ### ⚙️ Configuração do postcss.config.js
  ```javascript
  export default {
  plugins: {
      tailwindcss: {},
      autoprefixer: {},
    },
  };
  ```

  ---

  ## 📁 Criar / Ajustar src/index.css

  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```

  ---

  ## 🧩 Importações corretas no App.jsx
  **A ordem importa!**
  **PrimeReact → PrimeFlex → Tailwind**
  
  ```javascript
  
    // Estilos do PrimeReact
  import "primereact/resources/themes/lara-light-blue/theme.css";
  import "primereact/resources/primereact.min.css";
  import "primeicons/primeicons.css";

  // PrimeFlex (antes do Tailwind)
  import "primeflex/primeflex.css";

  // Tailwind (por último)
  import "./index.css";

  import { PrimeReactProvider } from "primereact/api";
  import Home from "./pages/Home/Home";

  function App() {
    return (
      <PrimeReactProvider>
        <Home />
      </PrimeReactProvider>
    );
  }

  export default App;

  ```
## ✅ Teste — Criar arquivo src/pages/Home/Home.jsx

```javascript
export default function Home() {
  return (
    <div className="card flex justify-content-center align-items-center gap-4 h-64 border border-gray-300">
      <div className="bg-blue-500 text-white px-4 py-2 rounded">Tailwind</div>
      <div className="bg-orange-500 text-white px-4 py-2 rounded">PrimeFlex</div>
    </div>
  );
}

```
    
## ▶️ Executar o Projeto

```
npm run dev

```

## ⚠️VS Code — Alertas como Unknown at rule @tailwind
Instale a extensão:  
```
Tailwind CSS IntelliSense
```
Opcional: adicionar no settings.json
```json
{
  "files.associations": {
    "*.css": "tailwindcss"
  },
  "css.lint.unknownAtRules": "ignore"
}

```
## 🆕 Usando Tailwind 4+ (se desejar futuramente)

Tailwind 4 separou o CLI e o comando mudou.

Instalar o CLI:
```bash
npm install -D @tailwindcss/cli

```
Rodar build/watch:
```bash
npx @tailwindcss/cli -i ./src/index.css -o ./dist/output.css --watch

```
[Documentação:](https://tailwindcss.com/docs/installation/tailwind-cli)
