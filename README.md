### **Starting from Scratch: Setting Up the SmartBit Project** 🚀  

The project is now configured with **Node.js, an API running on Docker, WSL2 integration**, and seamless **Linux-Windows interoperability**—an embedded workflow!  

## **Containers 🚀**  

### **🔹 How Do They Work?**  
- A **container** is created from an **image**, which defines the file system and application settings.  
- This image can be stored and shared via **registries** (e.g., Docker Hub).  
- Tools like **Docker and Kubernetes** help orchestrate and manage multiple containers.  

### **🔹 Benefits for Developers:**  
✔️ Replicable development environments  
✔️ Simplified production deployment  
✔️ Compatibility across different operating systems  

Containers have **revolutionized** software development and IT infrastructure, making processes **more efficient and scalable**! 🚀🐳  


## **Step-by-Step: SmartBit Project Setup**  

### **1️⃣ Install Git Bash for Windows**  
Git Bash provides a Unix-like terminal on Windows.  

1. Download Git Bash from the official site:  
   🔗 [https://git-scm.com/downloads](https://git-scm.com/downloads)  
2. Run the installer and follow the recommended setup, keeping **Windows Terminal integration enabled**.  
3. After installation, open **Git Bash** and configure your user details:  
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```  
4. Verify the installation:  
   ```bash
   git --version
   ```

---

### **2️⃣ Create Project Directories**  

1. In **Git Bash**, navigate to your preferred workspace:  
   ```bash
   cd /c/Users/YourUsername/Projects
   ```
2. Create the **SmartBit** project folder and subdirectories:  
   ```bash
   mkdir SmartBit && cd SmartBit
   mkdir api web
   ```

---

### **3️⃣ Set Up Git Repository**  

1. Initialize a Git repository at the root of the project:  
   ```bash
   git init
   ```
2. Create a `.gitignore` file to exclude unnecessary files:  
   ```bash
   touch .gitignore
   echo "node_modules/" >> .gitignore
   echo ".env" >> .gitignore
   ```
3. Check ignored files:  
   ```bash
   git status
   ```

---

### **4️⃣ Configure Node.js and Start the Project**  

1. Install **Node.js** (if not already installed):  
   🔗 [https://nodejs.org/](https://nodejs.org/)  
2. Verify installation:  
   ```bash
   node -v
   npm -v
   ```
3. Set up a project inside the **api** folder:  
   ```bash
   cd api
   npm init -y
   ```
4. Install **Express.js** to create the API:  
   ```bash
   npm install express
   ```
5. Create a `server.js` file:  
   ```bash
   touch server.js
   ```
6. Edit `server.js` to create a basic server:  
   ```javascript
   const express = require('express');
   const app = express();

   app.get('/', (req, res) => {
       res.send('SmartBit API is running!');
   });

   app.listen(3000, () => {
       console.log('Server is running on port 3000');
   });
   ```
7. Run the API to test:  
   ```bash
   node server.js
   ```

---

### **5️⃣ Install Docker Desktop with WSL2**  

1. Download Docker Desktop:  
   🔗 [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)  
2. During installation, enable the option **"Use WSL2 instead of Hyper-V"**.  
3. Restart your PC and open **Docker Desktop**.  
4. In **Docker Desktop**, go to **Settings > Resources > WSL Integration** and enable WSL2 integration.  

---

### **6️⃣ Set Up WSL2 and Install a Linux Distribution**  

1. Install WSL2 with Linux distribution support:  
   ```powershell
   wsl --install
   ```
2. List available distributions:  
   ```powershell
   wsl --list --online
   ```
3. Install Ubuntu (or another preferred distro):  
   ```powershell
   wsl --install -d Ubuntu
   ```
4. Set WSL2 as the default version:  
   ```powershell
   wsl --set-default-version 2
   ```

---

### **7️⃣ Run a Docker Container with Node.js**  

1. Inside the **api** folder, create a `Dockerfile`:  
   ```dockerfile
   FROM node:18

   WORKDIR /app
   COPY package.json ./
   RUN npm install
   COPY . .

   CMD ["node", "server.js"]
   ```
2. Create a `docker-compose.yml` file to manage services:  
   ```yaml
   version: '3'
   services:
     api:
       build: .
       ports:
         - "3000:3000"
       volumes:
         - .:/app
       command: npm start
   ```
3. In **Git Bash** or the WSL2 terminal, run the container:  
   ```bash
   docker-compose up -d
   ```
4. Check if the API is running:  
   ```bash
   curl http://localhost:3000
   ```

---

### **8️⃣ Running Two Operating Systems Simultaneously**  

Now, your development environment is running **Windows and Linux at the same time**, leveraging **WSL2 for seamless Docker integration**.  

- **From Windows**, you can access API files via File Explorer:  
  ```
  \\wsl$\Ubuntu\home\your-username\SmartBit\api
  ```
- **From Linux (WSL2)**, you can execute commands and develop natively in the terminal without needing dual boot.  

---

### **9️⃣ Finalizing and Pushing Code to GitHub**  

1. Go back to the project root and add the remote repository:  
   ```bash
   git remote add origin https://github.com/your-username/SmartBit.git
   ```
2. Add files and commit the changes:  
   ```bash
   git add .
   git commit -m "Initial setup of the SmartBit project"
   git push -u origin main
   ```

---

With this setup, your project is now fully configured with **Node.js, an API running in Docker, WSL2 integration, and GitHub version control**. 🚀  


Começando do zero o projeto está configurado com Node.js, API no Docker, integração WSL2 integração entre Linux e Windows, trabalho embarcado. 🚀

EM PORTUGUÊS

Contêineres 🚀

🔹 Como Funcionam?

Um contêiner é criado a partir de uma imagem, que define o sistema de arquivos e as configurações da aplicação.
Essa imagem pode ser armazenada e compartilhada através de registries (ex: Docker Hub).
Ferramentas como Docker e Kubernetes ajudam na orquestração e gerenciamento de múltiplos contêineres.
🔹 Uso para Desenvolvedores:
✔️ Ambientes de desenvolvimento replicáveis
✔️ Implantação simplificada em produção
✔️ Compatibilidade entre diferentes sistemas operacionais

Os contêineres revolucionaram o desenvolvimento e a infraestrutura de TI, tornando os processos mais eficientes e escaláveis! 🚀🐳

## **Passo a Passo: Configuração do Projeto SmartBit**  

### **1. Instalar o Git Bash for Windows**  
O Git Bash fornece um terminal Unix-like no Windows.  

1. Baixe o instalador do Git Bash no site oficial:  
   🔗 [https://git-scm.com/downloads](https://git-scm.com/downloads)  
2. Execute o instalador e siga os passos recomendados, mantendo a opção de integração com o Windows Terminal.  
3. Após a instalação, abra o **Git Bash** e configure seu usuário e e-mail:  
   ```bash
   git config --global user.name "Seu Nome"
   git config --global user.email "seuemail@email.com"
   ```  
4. Verifique a instalação com:  
   ```bash
   git --version
   ```

---

### **2. Criar Diretórios do Projeto**  

1. No **Git Bash**, navegue até a pasta onde deseja criar o projeto:  
   ```bash
   cd /c/Users/SeuUsuario/Projetos
   ```
2. Crie a pasta do projeto **SmartBit** e suas subpastas:  
   ```bash
   mkdir SmartBit && cd SmartBit
   mkdir api web
   ```

---

### **3. Configurar o Repositório Git**  

1. Inicialize o repositório na raiz do projeto:  
   ```bash
   git init
   ```
2. Crie um arquivo `.gitignore` para ignorar arquivos desnecessários:  
   ```bash
   touch .gitignore
   echo "node_modules/" >> .gitignore
   echo ".env" >> .gitignore
   ```
3. Confirme os arquivos ignorados:  
   ```bash
   git status
   ```

---

### **4. Configurar o Node.js e Iniciar o Projeto**  

1. Instale o **Node.js** (se ainda não tiver):  
   🔗 [https://nodejs.org/](https://nodejs.org/)  
2. Verifique a instalação:  
   ```bash
   node -v
   npm -v
   ```
3. Configure um projeto na pasta **api**:  
   ```bash
   cd api
   npm init -y
   ```
4. Instale o **Express.js** para criar a API:  
   ```bash
   npm install express
   ```
5. Crie um arquivo `server.js`:  
   ```bash
   touch server.js
   ```
6. Edite `server.js` para criar um servidor básico:  
   ```javascript
   const express = require('express');
   const app = express();

   app.get('/', (req, res) => {
       res.send('API SmartBit rodando!');
   });

   app.listen(3000, () => {
       console.log('Servidor rodando na porta 3000');
   });
   ```
7. Execute a API para testar:  
   ```bash
   node server.js
   ```

---

### **5. Instalar Docker Desktop com WSL2**  

1. Baixe o Docker Desktop:  
   🔗 [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)  
2. Durante a instalação, habilite a opção **"Use WSL2 instead of Hyper-V"**.  
3. Reinicie o PC e abra o **Docker Desktop**.  
4. No **Docker Desktop**, vá em **Settings > Resources > WSL Integration** e ative a integração com o WSL2.  

---

### **6. Configurar o WSL2 e Instalar uma Distribuição Linux**  

1. Instale o WSL2 com suporte a distribuições Linux:  
   ```powershell
   wsl --install
   ```
2. Liste as distribuições disponíveis:  
   ```powershell
   wsl --list --online
   ```
3. Instale o Ubuntu (ou outra de sua preferência):  
   ```powershell
   wsl --install -d Ubuntu
   ```
4. Defina o WSL2 como padrão:  
   ```powershell
   wsl --set-default-version 2
   ```

---

### **7. Executar o Contêiner Docker com Node.js**  

1. Na pasta **api**, crie um arquivo `Dockerfile`:  
   ```dockerfile
   FROM node:18

   WORKDIR /app
   COPY package.json ./
   RUN npm install
   COPY . .

   CMD ["node", "server.js"]
   ```
2. Crie um arquivo `docker-compose.yml` para gerenciar os serviços:  
   ```yaml
   version: '3'
   services:
     api:
       build: .
       ports:
         - "3000:3000"
       volumes:
         - .:/app
       command: npm start
   ```
3. No Git Bash ou terminal do WSL2, execute o contêiner:  
   ```bash
   docker-compose up -d
   ```
4. Verifique se a API está rodando:  
   ```bash
   curl http://localhost:3000
   ```

---

### **8. Trabalhando com Dois Sistemas Operacionais ao Mesmo Tempo**  

Agora, seu ambiente está rodando **Windows e Linux ao mesmo tempo**, usando o **WSL2** para integração perfeita com o Docker.  

- **No Windows**, você pode acessar os arquivos da API pelo Explorer em:  
  ```
  \\wsl$\Ubuntu\home\seu-usuario\SmartBit\api
  ```
- **No Linux (WSL2)**, você pode executar comandos e desenvolver diretamente no terminal sem necessidade de dual boot.  

---

### **9. Finalizando e Subindo o Código para o GitHub**  

1. Volte à raiz do projeto e inicialize o repositório remoto:  
   ```bash
   git remote add origin https://github.com/seu-usuario/SmartBit.git
   ```
2. Adicione os arquivos e faça o commit:  
   ```bash
   git add .
   git commit -m "Configuração inicial do projeto SmartBit"
   git push -u origin main
   ```

Com isso, o projeto está configurado com Node.js, API no Docker, integração WSL2 e GitHub. 🚀  
