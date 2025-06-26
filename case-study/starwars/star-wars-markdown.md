# Diagrama UML - Avaliação Star Wars

Este repositório contém a modelagem UML em MarkDown referente à Avaliação Star Wars. Para a criação da UML foi utilizado a tecnologia Astah.

## Classe Pessoa
**Atributos:**
- nome: String
- sobrenome: String
- sexo: String

**Métodos:**
+ imprime(): void
+ pessoa(): void
+ pessoa(n: int, sn: int): void
+ pessoa(n: int, sn: int, s: int): void

---

## Classe Jedi
**Herança:** extends Pessoa

**Atributos:**
- titulo: String

**Métodos:**
+ patiente(): void
+ jedi(nome: String, sobrenome: String): void
+ imprime(): void

**Associação:**
- weapons: ArrayList<Weapon> (relação 1 para muitos)

---

## Classe Sith
**Herança:** extends Pessoa

**Atributos:**
- titulo: String

**Métodos:**
+ lightning(nome: String, sobrenome: String): void
+ imprime(): void

**Associação:**
- weapons: ArrayList<Weapon> (relação 1 para muitos)

---

## Classe Force (Interface)
**Métodos:**
+ mindControl(): void
+ farseeig(): void
+ telepath(): void
+ levitation(): void

**Implementação:**
- Implementada por Jedi (linha tracejada)
- Implementada por Sith (linha tracejada)

---

## Classe Weapon
**Atributos:**
- descricao: String
- dano: int

**Métodos:**
+ weapon(): void
+ drop(): Weapon
+ pickup(): Weapon

**Relações:**
- Associação com Jedi (0..* weapons)
- Associação com Sith (0..* weapons)

---

## Classes Filhas de Weapon

### Classe Blast
**Herança:** extends Weapon

**Métodos:**
- + shot(): void

### Classe Saber
**Herança:** extends Weapon

**Métodos:**
- + slash(): void

---

## Relacionamentos

1. **Herança:**
   - Jedi herda de Pessoa
   - Sith herda de Pessoa
   - Blast herda de Weapon
   - Saber herda de Weapon

2. **Implementação:**
   - Jedi implementa Force
   - Sith implementa Force

3. **Associação:**
   - Jedi possui 0..* Weapon
   - Sith possui 0..* Weapon

4. **Composição:**
   - Weapon é composta por Blast e Saber (especialização)

   ---

   tecnologia utilizada: Astah