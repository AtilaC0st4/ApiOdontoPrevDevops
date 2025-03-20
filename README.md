Aqui está o README corrigido e formatado em **Markdown**:  

```markdown
# **ApiOdontoPrevDevops**  
## **OdontoPrev API**  

### **Integrantes do Grupo**  
- **Átila Costa** - RM552650  
- **Gabriel Leal** - RM553779  
- **Gabriel Plasa** - RM553527  

---  

## **Descrição do Projeto**  
A **OdontoPrev API** é uma aplicação desenvolvida em **ASP.NET Core Web API** que permite aos usuários registrar escovações dentárias. Além disso, a API oferece endpoints para gerenciar usuários e seus respectivos registros de escovação.  

---  

## **Arquitetura**  

A API foi desenvolvida utilizando uma **arquitetura monolítica**, pois essa abordagem foi considerada a mais adequada para o escopo do projeto.  

### **Justificativa da Arquitetura Monolítica**  
1. **Simplicidade**: A arquitetura monolítica facilita o desenvolvimento, os testes e a implantação, especialmente para projetos de pequeno e médio porte.  
2. **Facilidade de Manutenção**: Como o projeto não exige alta escalabilidade nem isolamento rigoroso de funcionalidades, essa abordagem permite um desenvolvimento mais eficiente.  
3. **Integração**: Todos os componentes do sistema (controllers, models, services) estão centralizados, o que simplifica a comunicação entre eles.  

### **Componentes da Arquitetura**  
- **Controllers**: Responsáveis por receber requisições HTTP e retornar as respostas apropriadas.  
- **Models**: Representam as entidades do sistema (usuários e registros de escovação).  
- **DbContext**: Gerencia a conexão com o banco de dados Oracle e as operações de CRUD.  
- **Swagger/OpenAPI**: Fornece documentação interativa da API.  

---  

## **Design Patterns Utilizados**  

### **Singleton**  
- **Onde foi aplicado**: No gerenciador de configurações (`AppSettings`), que é injetado como um serviço singleton no `Program.cs`.  
- **Justificativa**: O padrão Singleton garante que apenas uma instância do `AppSettings` seja criada e compartilhada em toda a aplicação, evitando duplicação e garantindo consistência.  

---  

## **Deploy da API**  

A API está hospedada na Azure e pode ser acessada através do seguinte link:  

🔗 **[Documentação da API (Swagger)](https://apiodontoprev.azurewebsites.net/swagger/index.html)**  

---  

## **Instruções para Rodar a API Localmente**  

### **Pré-requisitos**  
Antes de rodar a API, certifique-se de ter os seguintes requisitos instalados:  
- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)  
- [Oracle Database](https://www.oracle.com/database/) (ou um servidor Oracle disponível)  
- [Visual Studio](https://visualstudio.microsoft.com/)  

### **Passos para Execução**  

1. **Clone o repositório**:  
   ```bash
   git clone https://github.com/AtilaC0st4/ApiOdontoPrevDevops.git
   cd ApiOdontoPrevDevops
   ```

2. **Configure a conexão com o banco de dados**:  
   - No arquivo `appsettings.json`, altere a string de conexão para apontar para seu banco de dados Oracle:  
     ```json
     "ConnectionStrings": {
       "DefaultConnection": "Sua_String_de_Conexão"
     }
     ```  

3. **Aplicar Migrações (se necessário)**:  
   Execute os seguintes comandos para gerar e aplicar as migrações no banco de dados:  
   ```bash
   dotnet ef migrations add NomeDaMigration
   dotnet ef database update
   ```  

4. **Executar a API**:  
   ```bash
   dotnet run
   ```  
   A API estará disponível localmente em `http://localhost:5000` ou `https://localhost:5001`.  

5. **Acessar a Documentação**:  
   - Abra o navegador e acesse:  
     🔗 `https://localhost:5001/swagger/index.html`  

---  
