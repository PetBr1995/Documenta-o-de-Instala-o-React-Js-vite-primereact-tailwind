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

    
