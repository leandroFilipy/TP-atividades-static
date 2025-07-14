# 📘 Estudo: Membros Estáticos em Java (Variáveis e Métodos)

Este repositório documenta um estudo detalhado sobre o comportamento de variáveis e métodos `static` na linguagem Java, incluindo boas práticas, erros comuns e exemplos corrigidos.

---

## ✅ Análise de Casos

### 1. Chamada de método ou variável estática pela instância
> **Comentário:** Pode até funcionar, porém não é recomendável. O ideal é chamar diretamente pela **classe**, não pela instância.  
> **Exemplo não recomendado:**  
> `objeto.metodoEstatico();`  
> **Forma correta:**  
> `Classe.metodoEstatico();`

---

### 2. Criação de instâncias e variáveis estáticas
> A cada criação de uma instância, a variável estática `totalItens` aumenta em 1.  
> Isso ocorre porque ela é compartilhada entre todas as instâncias.

---

### 3. Valor compartilhado
> Quando `Produto.totalItens` é definido como `0`, **todos os objetos enxergarão esse valor**, já que é uma variável estática e pertence à classe, não à instância.

---

### 4. Método estático chamando método não estático
> ❌ Isso é um erro. Um método estático **não pode acessar diretamente** membros não estáticos da classe.  
> **Correção:** Tornar o método chamado também `static` ou acessar por meio de uma instância.

---

### 5. Construtores e incrementos
> O valor impresso será **2** porque o construtor foi chamado duas vezes, e ele possui um incrementador estático.  
> **Variável:** `static int contador = 0;`  
> **Resultado:** `contador == 2`

---

### 6. Impressão de mensagens
> Sim, o método está correto e exibirá uma mensagem de **bem-vindo** se for corretamente declarado como `static`.

---

### 7. Valor alterado para todas as instâncias
> Será impresso **20**, mesmo que inicialmente fosse `10`, pois a variável estática foi alterada. Todas as instâncias compartilham o **mesmo valor**.

---

### 8. Incremento com chamada de método
> A saída será **15**:  
> Variável estática iniciada em 5 → método a incrementa em 10 → resultado final: 15.

---

### 9. Erro por variável não ser estática
> ❌ O código **não compilará** porque tenta acessar uma variável de instância a partir de um contexto `static`.  
> **Correção:** declarar a variável como `static`.

---

### 10. Correção feita com `static`
> Com a variável corrigida para `static`, o código agora funcionará corretamente e poderá ser acessado diretamente de métodos estáticos.

---

### 11. Mensagem de boas-vindas
> ✅ Código correto. Será exibida a mensagem `Bem-vindo`.

---

### 12. Valor alterado reflete em todos os objetos
> Mesmo que `a = 10`, ao alterá-la para `20`, o valor será alterado **para todos**, inclusive `b`.  
> Isso ocorre porque `a` é `static`.

---

### 13. Variável sendo modificada por método
> Será impresso **15**.  
> A variável começa com 5 → método soma 10 → total = 15.

---

### 14. Variável `preco` não estática em método estático
> ❌ Erro de compilação.  
> **Solução:** Declarar `preco` como `static` para ser acessada de um método estático.

---

### 15. Tentativa de acessar variável não estática
> Também não funcionará, pois a variável ainda **não é estática**.

---

### 16. Incremento com chamada dupla de método
> Será imprimido **2**, pois o método foi chamado duas vezes e a variável estática foi incrementada a cada chamada.

---

## 🔁 Conclusões

- Variáveis e métodos `static` pertencem à **classe**, não à instância.
- Métodos `static` **não acessam diretamente membros não estáticos**.
- Variáveis `static` compartilham o **mesmo valor entre todas as instâncias**.
- **Boa prática:** Sempre acesse membros estáticos através da **classe**, e não de objetos.

---

## ✍️ Autor

**Leandro Filipy de Lima**  
Curso Técnico em Desenvolvimento de Sistemas – SENAI Jaraguá do Sul  
📅 Março de 2025

---

## 📄 Licença

Uso educacional e livre para estudos e repositórios acadêmicos.
