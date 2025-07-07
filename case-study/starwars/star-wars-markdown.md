```mermaid

classDiagram
    class Pessoa {
        - nome String
        - sobrenome String
        - sexo String
        + imprime() void
        + pessoa()
        + pessoa(n int, sn int)
        + pessoa(n int, sn int, s int)
    }
    
    class Jedi {
        - titulo String
        + patiente() void
        + jedi(nome String, sobrenome String)
        + imprime() void
    }
    
    class Force {
        <<interface>>
        + mindControl() void
        + farseeig() void
        + telepath() void
        + levitation() void
    }
    
    class Sith {
        - titulo String
        + lightning(nome String, sobrenome String) void
        + imprime() void
    }
    
    class Weapon {
        - descricao String
        - dano int
        + weapon()
        + drop() Weapon
        + pickup() Weapon
    }
    
    class Blast {
        + shot() void
    }
    
    class Saber {
        + slash() void
    }
    
    Pessoa <|-- Jedi
    Pessoa <|-- Sith
    
    Jedi ..|> Force
    Sith ..|> Force
    
    Weapon <|-- Blast
    Weapon <|-- Saber
    
    Jedi "1" -- "0..*" Weapon : -weapons ArrayList < Weapon>
    Sith "1" -- "0..*" Weapon : -weapons ArrayList < Weapon>