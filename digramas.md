# DISGRAMAS

## - DIAGRAMA DE COMPONENETES


```mermaid
graph TB
    Usuario["Usuario"] 
    Aprendiz["Aprendiz"]
    Ficha["Ficha"]
    Instructor["Instructor"]
    ProgramaFormacion["Prode Formacio"]
    CartaPractica["CarPractica"]
    Empresa["Empresa"]
    EstadoAprediz["EstaAprediz"]
    Modalidad["Modalidad"]

    style Usfill:lightgreen
    style Aprfill:lightgreen
    style Ficha fill:lightgreen
    style Instrfill:lightgreen
    style ProgramaFormfill:lightgreen
    style CartaPrafill:lightgreen
    style Emfill:lightgreen
    style EstadoApfill:lightgreen
    style Modafill:lightgreen

    Aprendiz --> |PerteFicha
    Ficha --> |Se GestInstructor
    Ficha --> |ReSeguimiento| Instructor
    Ficha --> |AsocProgramaFormacion
    Aprendiz --> |RequCartaPractica
    CartaPractica --> |IncEmpresa
    CartaPractica --> |IncEstadoAprediz
    CartaPractica --> |InModalidad

    linkStyle 0 stroke:#2stroke-width:2px;
    linkStyle 1 stroke:#2stroke-width:2px;
    linkStyle 2 stroke:#2stroke-width:2px;
    linkStyle 3 stroke:#2stroke-width:2px;
    linkStyle 4 stroke:#2stroke-width:2px;
    linkStyle 5 stroke:#2stroke-width:2px;
    linkStyle 6 stroke:#2stroke-width:2px;
    linkStyle 7 stroke:#2stroke-width:2px;
```