```mermaid 

classDiagram 
 Direction TB
    class I_Lawyer{
        <<interface>>
        +representClients() void
        +research() void 
        +analysis(String doc) void
        +fileDocument(String type) void
    }

       class I_OperatingOfficer{
        <<interface>>
        +supportExecutives() void
        +developPolicies() void 
        +coordinate() void
    }

       class I_Partner{
        <<interface>>
        +decisionMaking() void
        +profitRevenue() void
    }
    class TypeJob{ 
        <<abstract>>
    }
    class Person {
        -name String
        -surname String 
        -gender String 
        -job TypeJob
    }

    class Firm{
        -name String 
        -foundation LocalDate
        +listEmployes () String 
        +info() String 
    }

    class Law{
        -insuranceQuote String 
        -govApprovement String
        +info() String 

    }
    class Tech {
        -nonDisclosure String 
        -ipAdress String 
        +info() String 
    }
    class Attorney{
        -legalNumber int
    }

    class COO{

    }

    class NamePartner{

    }

    class Secretary{
        +organizing() void
        +prepare(String doc) void
    }

 TypeJob <|-- Attorney
 TypeJob <|-- Secretary

 Firm <|-- Law
 Firm <|-- Tech

 I_Lawyer <.. Attorney
 I_OperatingOfficer <.. COO
 I_Partner <.. COO
 I_Partner <.. NamePartner

 Secretary <|-- COO
 Attorney <|-- NamePartner 

 Person "1" -- "*" Firm : -employeers ArrayList < Person>
 Person -- TypeJob
 






