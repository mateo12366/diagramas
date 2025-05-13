# DISGRAMAS

- DIAGRAMA DE COMPONENETES

![alt text](img/componentes.png)

```mermaid
flowchart TD
    A[Inicio] --> B{¿Es día?}
    B -->|Sí| C[Saludar]
    B -->|No| D[Dormir]
    C --> E[Fin]
    D --> E
```