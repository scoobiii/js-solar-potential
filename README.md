MEX API Solar versão localmente (localhost) e também no **Google Cloud Platform (GCP)** utilizando o **Cloud Run**, incluindo o IP e a URL pública.

---

# ☀️ **Demo do Potencial Solar - Versão Local e GCP**

Este aplicativo demonstra como usar a **Solar API** para exibir informações sobre o potencial solar em um mapa personalizado do Google. O app pode ser executado localmente no **localhost** ou implantado na **Google Cloud Platform** (GCP) utilizando o **Cloud Run**.

---

## **Antes de Começar**

### **Requisitos:**
1. **Conta no Google Cloud Platform (GCP)**: Você precisará de uma conta do Google Cloud com um projeto ativado e com a conta de faturamento configurada.
2. **Ativar APIs no Google Cloud**: Ative a **Google Maps JavaScript API** e a **Solar API** no Console do Google Cloud.
   - Siga o guia de configuração do [Google Cloud Console](https://console.cloud.google.com/).
3. **Ambiente de Desenvolvimento**: Certifique-se de ter o **Node.js** instalado. Para verificar, execute `node -v` no terminal.

---

### **1. Clonar o Repositório**
Clone o repositório para sua máquina local:
```bash
git clone https://github.com/seu-repositorio/solar-potential.git
cd solar-potential
```

### **2. Instalar Dependências**
Instale todas as dependências necessárias para rodar o projeto:
```bash
npm install
```

---

## **Rodando Localmente no `localhost`**

### **Passos para Rodar Localmente:**

1. **Configuração da Chave da API**: Certifique-se de obter a chave da API do **Google Maps** e da **Solar API**, e adicione-a no arquivo `.env`:
    ```
    VITE_GOOGLE_MAPS_API_KEY="Sua chave da API do Google Maps"
    ```

2. **Rodar o App em Modo de Desenvolvimento**: Utilize o comando abaixo para iniciar o servidor local. O servidor será executado em `http://localhost:3000`:
    ```bash
    npm run dev
    ```

    Após rodar esse comando, abra o navegador e acesse `http://localhost:3000` para ver o aplicativo em funcionamento.

---

## **Rodando no Google Cloud Platform (GCP) com Cloud Run**

### **Passos para Implantar no GCP:**

1. **Autenticação e Preparação do Google Cloud**:
    - Faça login no Google Cloud:
      ```bash
      gcloud auth login
      ```
    - Selecione o projeto GCP no qual você deseja implantar o aplicativo:
      ```bash
      gcloud config set project "seu-id-do-projeto"
      ```

2. **Construir e Implantar no Cloud Run**:
    - Defina a região para a implantação:
      ```bash
      export LOCATION="us-central1"
      ```

    - Agora, construa e implante o aplicativo no **Cloud Run** com o comando abaixo. Isso criará e implantará o aplicativo automaticamente e atribuirá uma URL pública:
      ```bash
      gcloud run deploy "solar-potential" \
        --source="." \
        --region="$LOCATION" \
        --allow-unauthenticated
      ```

    - Após a execução do comando, o **Google Cloud** fornecerá uma URL pública com a qual você poderá acessar a versão do app rodando no GCP. O link será semelhante a:
      ```
      https://solar-potential-<hash>.uc.r.appspot.com
      ```

    - Para acessar o app, basta abrir o navegador e digitar a URL fornecida.

---

## **Estrutura de Pastas e Arquivos**

Aqui está a árvore de diretórios do projeto:

```
solar-potential/
│
├── public/                    # Arquivos públicos (ex: HTML, ícones)
│   └── index.html             # Arquivo principal HTML
├── src/                       # Código-fonte do aplicativo
│   ├── components/            # Componentes reutilizáveis
│   ├── pages/                 # Páginas do aplicativo
│   ├── services/              # Serviços de API e lógica de negócios
│   └── stores/                # Armazenamento de estado (Svelte)
├── .env                       # Arquivo de variáveis de ambiente (contém a chave da API)
├── package.json               # Gerenciador de pacotes e dependências
├── README.md                  # Este arquivo de documentação
├── tailwind.config.js         # Configurações do Tailwind CSS
└── vite.config.js             # Configurações do Vite
```

---

## **Rodando os Testes**

Antes de subir a API para o ambiente de produção (seja local ou GCP), é importante rodar os testes e garantir que tudo está funcionando corretamente.

1. **Verificação de Tipos**: Execute o comando abaixo para verificar se há erros de tipos no código:
    ```bash
    npm run check
    ```

2. **Verificação de Estilo de Código (Linting)**: Execute o comando abaixo para verificar problemas de formatação e estilo no código:
    ```bash
    npm run lint
    ```

3. **Formatação Automática do Código**: Para corrigir automaticamente qualquer problema de formatação:
    ```bash
    npm run format
    ```

4. **Testes Contínuos**: Caso queira rodar os testes continuamente durante o desenvolvimento, execute o seguinte comando para que os testes sejam executados automaticamente toda vez que você salvar um arquivo:
    ```bash
    npm run check:watch
    ```

---

## **URLs e Acessos**

- **Local**: A versão do aplicativo rodando localmente pode ser acessada via `http://localhost:3000`.
- **GCP (Cloud Run)**: A versão do aplicativo rodando no Google Cloud será acessada via URL pública fornecida pelo GCP, com formato semelhante a:
  ```
  https://solar-potential-<hash>.uc.r.appspot.com
  ```

---

## **Tech Stack**

- **Solar API**: Para obter dados sobre o potencial solar e configurações de painéis solares.
- **Google Maps**: Para exibir mapas interativos com a API do Google Maps.
- **Material Design 3**: Framework para componentes com Material Design.
- **SvelteKit**: Framework para desenvolvimento de aplicativos web reativos e declarativos.
- **Vite**: Ferramenta de build otimizada para desenvolvedores modernos.
- **Tailwind CSS**: Framework CSS para construção rápida de interfaces.
- **ESLint**: Ferramenta para análise estática do código.
- **Prettier**: Ferramenta para formatação automática de código.

---

## **Considerações Finais**

Este guia fornece instruções detalhadas para rodar o aplicativo de **Potencial Solar** tanto localmente quanto na **Google Cloud Platform (GCP)**. Siga as etapas para configurar, rodar os testes, e implantar a aplicação, garantindo que ela esteja funcionando corretamente antes de ser disponibilizada publicamente.

Caso encontre problemas, verifique as mensagens de erro e as configurações de sua conta Google Cloud para garantir que tudo esteja correto.

---
