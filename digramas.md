# DIAGRAMAS

## - DIAGRAMA DE COMPONENETES

```mermaid
graph TB
    Usuario["Usuario"] 
    Aprendiz["Aprendiz"]
    Ficha["Ficha"]
    Instructor["Instructor"]
    ProgramaFormacion["Programa de Formacio"]
    CartaPractica["Carta de Practica"]
    Empresa["Empresa"]
    EstadoAprediz["Estado de Aprediz"]
    Modalidad["Modalidad"]

    Aprendiz --> |Pertenece| Ficha
    Ficha --> |Se Gestiona| Instructor
    Ficha --> |Realiza Seguimiento| Instructor
    Ficha --> |Asociada| ProgramaFormacion
    Aprendiz --> |Requiere| CartaPractica
    CartaPractica --> |Incluye| Empresa
    CartaPractica --> |Incluye| EstadoAprediz
    CartaPractica --> |Incuye| Modalidad

    linkStyle 0 stroke:#2ecd71,stroke-width:2px;
    linkStyle 1 stroke:#2ecd71,stroke-width:2px;
    linkStyle 2 stroke:#2ecd71,stroke-width:2px;
    linkStyle 3 stroke:#2ecd71,stroke-width:2px;
    linkStyle 4 stroke:#2ecd71,stroke-width:2px;
    linkStyle 5 stroke:#2ecd71,stroke-width:2px;
    linkStyle 6 stroke:#2ecd71,stroke-width:2px;
    linkStyle 7 stroke:#2ecd71,stroke-width:2px;
```

*en este diagrama vemos que el* **Usuario** *no tiene una relacion directa con los demas componentes, 
solo se maneja los perfiles con sus roles para el ingreso a la app, luego tenemos un flujo donde el* **Aprendiz** 
*pertenece a un ficha la cual esta asociada con un* **Programa de Formacion** *y esta ficha es gestionada por un* **Instructor** *a la vez el aprendiz requere una* **Carta de practica** *que incluye de información* **Empresa, Estado Aprendiz y Modalidad**.

## -DIAGRAMA DE OBJETOS

```mermaid
 classDiagram
    class Usuario{
        idUsuario: "10245"
        contrasena:"***"
        nombre:"Julian"
        apellidos:"Salzar Pineda"
        cedula:"15895212"
        correo:"julian@gamilc.com"
        rol:"visualizar"
    }
    class Aprendices {
        numeroDeIdentificacion: 1054864001
        tipoIdentificacion: "TI"
        nombre: "Geraldine"
        apellidos: "Vasquez Gutierrez"
        correo: "gvg130704@gmail.com"
        telefono: "3228925330"
        fechaNacimiento: "2007-04-13"
        lugarNacimiento: "Manizales"
        direccion: "calle 2a N 5-55"
        ciudad:"Manizales"
    }

    class Ficha {
        idFicha: "2873707"
        fechaInicioEtapaLectiva: "2024-01-22"
        fechaFinEtapaLectiva: "2025-01-22"
        fechaInicioEtapaPractica: "2026-01-22"
        fechaFinEtapaPractica: "2026-07-22"
    }

    class Instructor{
        id_instructor: "28795631002"
        nombre: "Julian"
        apellidos:"Salazar Pineda"
        correo: "julian@gmail.com"
        telefono:"3258942022"
    }

    class ProgramaFormacion{
        idPrograma: "28792001"
        Nombre: "Analisis y Desarrollo de Software"
        perfilOcupacional: "analista de datos"
        version:"V2"
            
    }

    class CartaPractica{
        idCarta: "102486"
        numRadicadoSolicitud: "2545478887"
        numRadicadoAutorizacion: "2545478887"
        fechaCreacion:"2024-08-15"
        afiliacionARL:"SI"
        auxiloEconomico:"NO"
        voBoBienestar: "SI"
        sofiaPlus:"SI"
        fechaAfiliacionARL:"2024-08-12"
    }

    class Modalidad{
        idModalidad:"2048"
        tipo:"Presencial"
    }

    class EstadoAprendiz{
        idEstado:"25879"
        nombre:"Etapa Productiva"
    }

    class Empresa{
        idEmpresa:"25878454"
        nombre:"Emergia"
        direccion:"calle 24a 8-65"
        nit:"2158787"
        correo:"emergia@gmai.com"
        telefono:"325487854"
    }
            
    Aprendices -->  Ficha:Pertenece
    Ficha --> Instructor :se gestiona
    Instructor -->  Ficha:Realiza Segumiento
    Ficha --> ProgramaFormacion: Asociada
    Aprendices --> CartaPractica:Requiere
    CartaPractica -->Modalidad:Incluye
    CartaPractica --> EstadoAprendiz: Incluye
    CartaPractica -->Empresa:Incluye
```

*en el diagrama de objetos podemos ver el mismo flijo que en el digrama de componentes solo que en este podemos ver al detalle cada uno de los traubitos que tiene cada una de las clases involucradas en es sofware.*

## -DIAGRAMA DE CLASES

```mermaid
classDiagram
    class Usuario{
        +int IdUsuario
        +int contraseña
        +String Nombre
        +String Apellido
        +int Cedula
        +String Correo
        +String rol
        +RegistrarUnNuevoUsuario(Usuario) :void
        +EliminarDatosUsuario(Usuario) : void
        +SubirDatosUsuario(Usuario) :void
        +ActualizarDatosUsuario(Usuario) : void
        +VisualizarDatos(Usuario) : void
    
    }
    class Aprendices {
        +int NumIdentificacion
        +String Nombre
        +String Apellidos
        +String Correo
        +int Telefono
        +Date FechaNacimiento
        +string LugarNacimiento
        +String Direccion
        +String ciudad
        +String tipoIdentificacion
        +RegistrarAprendiz(Aprendices) : void
        +ActualizarDatosAprendiz(Aprendices) : void
        +EliminarDatosAprendiz(Aprendices) : void
        +SubirDatosAprendices(Aprendices) : void
        +VisualizarDatos(Aprendices) : void
    }

    class Ficha{
        +int idFicha
        +date FechaInicionEtapaLectiva
        +date FechaFinEtapaLectiva
        +date FechaInicioEtapaPractica
        +date FechaFinEtapaPractica
        +RegistrarFicha(Ficha) : void
        +EliminarFicha(Ficha):void
        +ActualizarDatosFicha(Ficha):void
        +SubirDatosFicha(Ficha) : void
        +VisualizarDatos(ficha) : void
    }
    class programaFormacion{
        +int idPrograma
        +String Nombreprograma
        +String PerfilOcupacional
        +String version
        +RegistrarProgramaFormacion(programaFormacion) : void
        +EliminarProgramaFormacion(programaFormacion) : void
        +Actualizar(programaFormacion): void
        +VisualizarDatos(programaFormacion) : void
    }
    class Instructor{
        +int idInstructor
        +int numeroDocumento
        +String Nombre
        +String Apellidos
        +String Correo
        +int Telefono
        +crearInstructor(Instructor) : void
        +ActualizarDatosInstructor(Instructor) : void
        +EliminarDatosInstructor(Instructor) : void
        +VisualizarDatos(Instructor) : void
    }
    class CartaPractica{
        +int IdCarta
        +int NumeroRadicadoSolicitud
        +int NumeroRadicadoAutorizacion
        +date FechaCreacion
        +String AfiliacionArl
        +bolean AuxilioEconomico
        +String VoboBienestar
        +bolean SofiaPlus
        +date FechaAfiliacionArl
        +CrearCarta(CartaPractica) : void
        +VisualizarDatos(CartaPractica) : void
    }
    class Modalidad{
        +int IdModalidad
        +String tipo
    }
    class EstadoAprendiz{
        +int IdEstado
        +String Nombre
        +ActualizarEstadoAprendiz(EstadoAprendiz): void
    }
    class Empresa{
        +int IdEmpresa
        +String Nombre
        +String Direccion
        +int NIT
        +String Correo
        +int Telefono
        +crearEmpresa(Empresa) : void
        +EliminarEmpresa(Empresa) : void
        +ActualizarDatosEmpresa(Empresa) : void
        +VisualizarDatos(Empresa) : void
    }

    Aprendices "0..*"-->"1" Ficha : Pertenece
    Ficha "1"-->"0..*" Instructor : Realiza_Seguimiento
    Ficha "0..*"-->"1" Instructor : Se_Gestiona
    Ficha "0..*"-->"1" programaFormacion : Asociar
    Aprendices "1"-->"0..*" CartaPractica : Requiere
    CartaPractica "0..*"-->"1" Modalidad : Incluye
    CartaPractica "0..*"-->"1" EstadoAprendiz : Incluye
    CartaPractica "0..*"-->"1" Empresa : Incluye
```

*En el diagrama de clases podemos observar adicinalmente todas las* **Funciones (Metodos)** *que se oueden realizar en cada una de las clases como:*  
- *Actualizar*  
- *Eliminar*  
- *Subir datos*  
- *Visualizar datos*

## DIGRAMA DE SECUENCIAS

```mermaid
sequenceDiagram
    actor Usuario
    participant EmpresaController
    participant BaseDeDatos

    Usuario ->> EmpresaController: crearEmpresa(datosEmpresa)
    activate EmpresaController
    EmpresaController ->> BaseDeDatos: validarDatos(datosEmpresa)
    activate BaseDeDatos
    BaseDeDatos -->> EmpresaController: válido
    deactivate BaseDeDatos

    EmpresaController ->> BaseDeDatos: guardarEmpresa(datosEmpresa)
    activate BaseDeDatos
    BaseDeDatos -->> EmpresaController: éxito
    deactivate BaseDeDatos

    EmpresaController -->> Usuario: "Empresa creada exitosamente"
    deactivate EmpresaController
```