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

    Aprendiz --> |PerteFicha
    Ficha --> |Se GestInstructor
    Ficha --> |ReSeguimiento| Instructor
    Ficha --> |AsocProgramaFormacion
    Aprendiz --> |RequCartaPractica
    CartaPractica --> |IncEmpresa
    CartaPractica --> |IncEstadoAprediz
    CartaPractica --> |InModalidad
```