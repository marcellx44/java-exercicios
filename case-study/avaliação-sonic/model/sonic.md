```mermaid

classDiagram
    class Direction {
        <<enumeration>>
        Front
        Back
        Up
        Down
    }
    
    class TipoObjeto {
        <<enumeration>>
        Ring
        Box
    }
    
    class Character {
        <<abstract>>
        - name: String
        - life: int
        - image: String
        - x: int
        - y: int
        + getCoordinates() String
        + moverDirection(Direction) void
    }
    
    class Sonic {
        - estaPulando: boolean
        + isEsperando() boolean
    }
    
    class Tails {
        + voar() void
    }
    
    class Monkey {
        + escalarArvore() void
    }
    
    class Environment {
        - name: String
        - image: String
        - width: int
        - height: int
        - score: int
        - time: double
        - qtdRings: int
        + colidiu(sonic: Sonic, tails: Tails, monkey: Character) void
        + showCharacter() void
        + showObjects() void
        + showPanel() void
    }
    
    class Object {
        - tipo: TipoObjeto
    }
    
    Character <|-- Sonic
    Character <|-- Tails
    Character <|-- Monkey
    
    Character "*" --* "1" Direction : uses
    
    Environment "1" o-- "*" Object : objects
    
    Object ..> TipoObjeto : uses