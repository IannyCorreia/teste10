# 🛋️ Furniro - E-commerce de Móveis

Bem-vindo ao **Furniro**, um projeto de e-commerce completo e moderno, desenvolvido com **React**, **TypeScript** e **Tailwind CSS**.

Este projeto não é apenas uma vitrine de produtos, mas uma aplicação web robusta com autenticação de usuário, gerenciamento de estado global, interações com APIs externas e hospedagem profissional na AWS.

📷[Demonstração do Site]: (https://drive.google.com/drive/folders/1xNdMT_YCgI81KeWWSgTfwxay9sivdj-S?usp=sharing)

---

## ✨ Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Principais Funcionalidades](#-principais-funcionalidades)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Rodar o Projeto Localmente](#-como-rodar-o-projeto-localmente)
- [Implantação na AWS EC2](#-implantação-na-aws-ec2)
- [Colaboradores](#-Colaboradores)

---

## 📝 Sobre o Projeto

O **Furniro** foi criado para simular um ambiente de e-commerce real, com foco na experiência do usuário e na qualidade do código.  

O projeto utiliza `JSON Server` para simular uma API de produtos e autenticação com o serviço **Clerk**.

---

## 🚀 Principais Funcionalidades

### 👤 Header e Navegação
- Autenticação com Clerk (Login/Cadastro via ícone de perfil)
- Navegação protegida: Página de contato acessível apenas por usuários logados
- Carrinho inteligente via overlay (sidebar)

### 🛒 Carrinho
- Gerenciado com Redux Toolkit
- Adição instantânea de produtos
- Quantidade dinâmica com atualização de subtotal e total
- Acesso rápido para páginas de Carrinho e Checkout

### ✅ Checkout
- Acesso restrito a usuários autenticados
- Formulário validado com React Hook Form + Zod
- Preenchimento automático de endereço via API do ViaCEP
- Toast de sucesso ao finalizar pedido com método de pagamento obrigatório

### 📞 Contato
- Acesso somente para usuários logados
- Nome e e-mail obrigatórios com validação
- Confirmação via Toast ao enviar

### 🧪 Testes
- Cobertura superior a 80% nas páginas Checkout e Contact
- Testes com Jest e React Testing Library
- 
  ![image](https://github.com/user-attachments/assets/ac1deb0c-ddf7-4ec9-805e-b72b44445b22)



---

## 🛠️ Tecnologias Utilizadas

- **Front-End:** React, TypeScript, Vite, Tailwind CSS  
- **Estado Global:** Redux Toolkit  
- **Roteamento:** React Router  
- **Formulários:** React Hook Form, Zod  
- **Testes:** Jest, React Testing Library  
- **Autenticação:** Clerk  
- **Back-End Fake:** JSON Server  
- **Hospedagem:** AWS EC2 + Nginx  
- **Versionamento:** Git & GitHub

---


## ⚙️ Como Rodar o Projeto Localmente
1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/IannyCorreia/furniro-web.git
    cd furniro-web
    ```

2.  **Instale as dependências:**
    ```bash
    npm install
    ```

3.  **Crie o arquivo de ambiente:**
    * Crie um arquivo chamado `.env.local` na raiz do projeto.
    * Adicione a sua chave publicável do Clerk:
        ```
        VITE_CLERK_PUBLISHABLE_KEY="pk_test_sua_chave_aqui"
        ```

4.  **Inicie o JSON Server:**
    * Em um terminal, rode o comando para iniciar o servidor de dados:
        ```bash
        npx json-server --watch public/db.json --port 3001
        ```

5.  **Inicie o projeto React:**
    * Em outro terminal, inicie a aplicação:
        ```bash
    npm run dev
        ```
    * Abra [http://localhost:5173] no seu navegador.

<br/>

☁️ Implantação na AWS EC2
A aplicação está hospedada em uma instância EC2 (t2.micro) da AWS, garantindo disponibilidade e performance. O processo de implantação envolveu:

Criação e Configuração da Instância: Lançamento de uma instância Amazon Linux com um Security Group configurado para permitir tráfego HTTP (porta 80) e SSH (porta 22).

Hospedagem de Mídia: Todas as imagens dos produtos e assets visuais foram armazenadas em um Bucket S3 da AWS para otimizar o carregamento e a escalabilidade.
![image](https://github.com/user-attachments/assets/6cacf345-ada9-40c2-b235-96c525910ed6)

Preparação do Ambiente: Instalação do Git, Node.js (via NVM) e do servidor web Nginx.

Deploy do Código: Clonagem do repositório a partir do GitHub e construção da versão de produção do projeto com npm run build.

Configuração do Nginx: Edição da configuração do Nginx para servir o conteúdo da pasta dist gerada e para lidar corretamente com as rotas do React Router.



<br/>
## ✒️ Colaboradores

- **Ianny Correia**
- **Ana Julia Braghim**
- **Felipe Fidelis**
- **Luis Henrique Rodrigues**
