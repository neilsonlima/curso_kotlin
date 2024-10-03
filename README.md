# DidaCoin - Projeto de Criptomoeda Didática

## 1. Visão Geral do Projeto
A DidaCoin é uma criptomoeda desenvolvida para fins educacionais, demonstrando os princípios fundamentais de blockchain e desenvolvimento de software usando Kotlin no backend e Vue.js no frontend.

## 2. Objetivos
- Criar uma criptomoeda funcional básica
- Demonstrar boas práticas de desenvolvimento de software
- Fornecer documentação clara e educativa

## 3. Stack Tecnológica

### 3.1 Backend (Kotlin)
- Framework: Spring Boot
- Build Tool: Gradle
- Testes: JUnit 5 com Mockk
- Documentação API: SpringDoc OpenAPI

### 3.2 Frontend (Vue.js)
- Vue.js 3 com Composition API
- TypeScript para type safety
- Pinia para gerenciamento de estado
- Vue Router para navegação
- Vite como build tool

### 3.3 Infraestrutura
- Docker para containerização
- PostgreSQL para persistência
- Redis para caching

## 4. Estrutura do Projeto

### 4.1 Backend (Kotlin)
```
src/
├── main/
│   ├── kotlin/
│   │   └── com/
│   │       └── didacoin/
│   │           ├── Application.kt
│   │           ├── blockchain/
│   │           │   ├── Block.kt
│   │           │   ├── Blockchain.kt
│   │           │   └── Transaction.kt
│   │           ├── wallet/
│   │           │   └── Wallet.kt
│   │           ├── api/
│   │           │   └── controllers/
│   │           └── config/
│   └── resources/
│       └── application.yml
└── test/
    └── kotlin/
        └── com/
            └── didacoin/
```

### 4.2 Frontend (Vue.js)
```
src/
├── assets/
├── components/
│   ├── wallet/
│   └── blockchain/
├── views/
├── router/
├── stores/
├── types/
└── App.vue
```

## 5. Práticas de Desenvolvimento

### 5.1 Kotlin Best Practices
- Uso de data classes para models
- Coroutines para operações assíncronas
- Extension functions para código limpo
- Null safety com tipos nullable

### 5.2 Vue.js Best Practices
- Composables para lógica reutilizável
- Single File Components
- TypeScript para type safety
- Convenções de nomenclatura Vue

## 6. Implementação - Principais Componentes

### 6.1 Blockchain Core (Kotlin)
```kotlin
data class Block(
    val index: Long,
    val timestamp: Long,
    val transactions: List<Transaction>,
    val previousHash: String,
    val hash: String,
    val nonce: Long
)

data class Transaction(
    val id: String,
    val sender: String,
    val recipient: String,
    val amount: BigDecimal,
    val timestamp: Long
)

class Blockchain {
    private val blocks: MutableList<Block> = mutableListOf()
    
    fun addBlock(transactions: List<Transaction>): Block {
        // Implementação
    }
    
    fun isValid(): Boolean {
        // Implementação
    }
}
```

### 6.2 API Endpoints
```kotlin
@RestController
@RequestMapping("/api/v1")
class BlockchainController(private val blockchainService: BlockchainService) {
    
    @GetMapping("/blocks")
    fun getBlocks(): List<Block> {
        return blockchainService.getBlocks()
    }
    
    @PostMapping("/transactions")
    fun createTransaction(@RequestBody transaction: Transaction): Transaction {
        return blockchainService.addTransaction(transaction)
    }
}
```

## 7. Roadmap de Implementação

### Sprint 1: Setup (1 semana)
- Configurar projeto Kotlin com Spring Boot
- Configurar projeto Vue.js
- Definir estrutura de dados básica

### Sprint 2: Core Blockchain (2 semanas)
- Implementar estruturas de Block e Transaction
- Desenvolver lógica de mineração básica
- Criar testes unitários

### Sprint 3: API e Integração (2 semanas)
- Desenvolver endpoints REST
- Implementar integração com banco de dados
- Criar documentação da API

### Sprint 4: Frontend Básico (2 semanas)
- Desenvolver interface de usuário para visualização da blockchain
- Implementar formulário de criação de transação
- Integrar com API backend

## 8. Próximos Passos Imediatos
1. Setup do ambiente de desenvolvimento
   - Instalar JDK, Kotlin, Node.js
   - Configurar IDE (IntelliJ IDEA recomendado)
2. Criar repositório Git
3. Iniciar projeto Kotlin com Spring Boot
4. Iniciar projeto Vue.js
5. Desenvolver primeiro endpoint e componente

