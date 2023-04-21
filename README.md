# Configrando-RTL-com-vite-vitest

 Criar uma nova aplicação Vite se ainda não foi criada npm create vite
Siga os passos para criar uma aplicação React com JS.

 Instalar as dependências necessárias
npm i -D vitest jsdom @testing-library/jest-dom @testing-library/react @testing-library/user-event 
 Criar um arquivo chamado setupTests.js na raíz do projeto e adicionar:
import '@testing-library/jest-dom';
 No arquivo vite.config.js, adicionar em defineConfig os códigos não comentados abaixo:
// vite.config.js

// ...

// export default defineConfig({
//   plugins: [react()],
  test: {
    globals: true,
    environment: 'jsdom',
    setupFiles: './setupTests.js',
    css: true,
    coverage: {
      reporter: ['text', 'json', 'html'],
    },
    reporters: ['verbose'],
  },
// })
 No arquivo package.json, adicionar o script de teste e de coverage :
// package.json

//...

"scripts": {
//   "dev": "vite --open",
//   "build": "vite build",
//   "preview": "vite preview",
  "test": "vitest",
  "coverage": "vitest run --coverage",
},

// ...
Pronto, tudo configurado para usar vitest + RTL no seu projeto React com Vite. tada
