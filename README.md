
# API REST - Gerenciador de Condomínios

Esta é uma API REST para gerenciamento de condomínios, permitindo a adição, edição, remoção e listagem de condomínios, apartamentos, moradores e funcionários.

## Tecnologias Utilizadas
- Java 17+
- Spring Boot
- Spring Data JPA
- PostgreSQL
- Docker

---

## Endpoints

### **Condomínios**

#### ➤ Criar um Condomínio
```http
POST /api/v1/condominios
```  
**Exemplo de Requisição:**
```json
{
  "nome": "TESTE",
  "notas": "Condomínio de alto padrão",
  "endereco": {
    "logradouro": "Rua Principal",
    "numero": "588",
    "complemento": "nn",
    "bairro": "Fundos",
    "cidade": "Florianopolis",
    "uf": "SC",
    "cep": "88888-888"
  }
}
```  

#### ➤ Atualizar um Condomínio
```http
PUT /api/v1/condominios/{id}
```  
**Exemplo:**
```http
PUT /api/v1/condominios/1
```  

#### ➤ Remover um Condomínio
```http
DELETE /api/v1/condominios/{id}
```  
**Exemplo:**
```http
DELETE /api/v1/condominios/3
```  

#### ➤ Buscar um Condomínio por ID
```http
GET /api/v1/condominios/{id}
```  
**Exemplo:**
```http
GET /api/v1/condominios/1
```  

---

### **Apartamentos**

#### ➤ Listar Todos os Apartamentos
```http
GET /api/v1/condominios/apartamentos
```  

#### ➤ Adicionar um Apartamento a um Condomínio
```http
POST /api/v1/condominios/apartamentos/{idCondominio}
```  
**Exemplo:**
```json
{
    "numero" : "2025",
    "bloco" : "BB"
}
```  

#### ➤ Atualizar um Apartamento
```http
PUT /api/v1/condominios/apartamentos/{idCondominio}/{idApartamento}
```  
**Exemplo:**
```http
PUT /api/v1/condominios/apartamentos/1/1
```  

#### ➤ Remover um Apartamento
```http
DELETE /api/v1/condominios/apartamentos/{idCondominio}/{idApartamento}
```  
**Exemplo:**
```http
DELETE /api/v1/condominios/apartamentos/5/1
```  

#### ➤ Buscar um Apartamento por ID
```http
GET /api/v1/condominios/apartamentos/{id}
```  
**Exemplo:**
```http
GET /api/v1/condominios/apartamentos/2
```  

---

### **Moradores**

#### ➤ Adicionar um Morador a um Apartamento
```http
POST /api/v1/condominios/apartamentos/moradores/{idCondominio}/{idApartamento}/morador
```  
**Exemplo:**
```json
{
    "nome" : "HELO",
    "cpf" : "11122288817",
    "telefone": "8796347824",
    "email" :"teste@teste.com"
}
```  

#### ➤ Atualizar um Morador
```http
PUT /api/v1/condominios/apartamentos/moradores/{idCondominio}/{idApartamento}/{idMorador}/morador
```  
**Exemplo:**
```http
PUT /api/v1/condominios/apartamentos/moradores/1/2/3/morador
```  

#### ➤ Buscar um Morador por CPF
```http
GET /api/v1/condominios/apartamentos/moradores/morador/cpf/{cpf}
```  
**Exemplo:**
```http
GET /api/v1/condominios/apartamentos/moradores/morador/cpf/88899944447
```  

#### ➤ Remover um Morador
```http
DELETE /api/v1/condominios/apartamentos/moradores/{idCondominio}/{idApartamento}/{idMorador}/morador
```  
**Exemplo:**
```http
DELETE /api/v1/condominios/apartamentos/moradores/1/1/1/morador
```  

---

### **Funcionários**

#### ➤ Adicionar um Funcionário a um Condomínio
```http
POST /api/v1/condominios/funcionarios/{idCondominio}
```  
**Exemplo:**
```json
{
    "nome" : "Yasmin Sebastiana Fabiana Almeida",
    "cpf" : "617.766.170-02",
    "telefone" :"(11)555555555",
    "cargo": "SINDICA"
}
```  

#### ➤ Atualizar um Funcionário
```http
PUT /api/v1/condominios/funcionarios/{idCondominio}/{idFuncionario}
```  
**Exemplo:**
```http
PUT /api/v1/condominios/funcionarios/1/2
```  

#### ➤ Remover um Funcionário
```http
DELETE /api/v1/condominios/funcionarios/{idCondominio}/{idFuncionario}
```  
**Exemplo:**
```http
DELETE /api/v1/condominios/funcionarios/2/2
```  

#### ➤ Buscar um Funcionário por CPF
```http
GET /api/v1/condominios/funcionarios/{cpf}
```  
**Exemplo:**
```http
GET /api/v1/condominios/funcionarios/11144455577
```  

---

## Como Executar a API

### Usando Docker

1. Clone o projeto para sua máquina, "Git clone" e execute o seguinte comando:
   ```sh
    docker-compose up -d --build
   ```  

2. Execute a aplicação em um container Docker:
   ```sh
   docker-compose up
   ```  

3. Acesse a API no navegador ou em qualquer ferramenta de testes (como Postman):
   ```
   http://localhost:8080/api/v1/condominios
   ```  

4.  * OBS:  para obter dados validos como cpf, recomendo o uso do "4devs"
   ```
   https://www.4devs.com.br/gerador_de_cpf
   ```
   

>>>> Desenvolvido por:  Deusley Diego 
