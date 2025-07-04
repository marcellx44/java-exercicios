```mermaid 

classDiagram 
    class Person {
        -name String
        -surname String 
        -gender String 
        -job TypeJob
    }

    class Attorney{

    }

    class COO{

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

    class NamePartner{

    }

    class Secretary{
        +organizing() void
        +prepare(String doc) void
    }

    class Tech {
        -nonDisclosure String 
        -ipAdress String 
        +info() String 
    }

    class TypeJob{ 
        <<abstract>>
    }
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


