# Propuesta_planet_Solar

## Razonamiento

Ya cerca de cumplir un mes en cotizaciones he notado, a nivel personal, que uno de las razones principales para los retrasos es depender de un mínimo de 3 plataformas simultáneamente, plataformas que no tienen como compartir información entre ellas. El depender de tantas herramientas, tomando datos de una para ser llevados a la otra es espacio propenso para el error y tiene la consecuencia de trabajo extra al reparar ese error.

Tanta posibilidad de mano humana en ciertos procesos, a veces sin una validación completa de la información (formatos, contenido, etc, etc, etc), hace vulnerable la cadena de producción y genera retrasos que pueden ser solventados a través de un sistema informático que unifique los siguientes elementos:

1. **Jotform**: Al crear una base de datos relacional, cada cliente seria un ID único al cual se le pueden hacer varias cotizaciones de ser necesario.
2. **GoFormz**: Con la información del cliente creada, se puede usar la API de goformz para generar los documentos necesarios y la información necesaria a partir de la que ya existe en el modelo del cliente, reduciendo el procesar la información y rellenando solo los campos que no se poseen. A su vez todos los documentos apuntaran directamente hacia el cliente y el cliente apuntara directamente a todos los documentos.
3.**Lista de Precios, Calculadora de consumo**: Al ser ambos hojas de calculo existentes para procesar la información, se puede generar un espacio dentro de la misma plataforma que haga exactamente lo mismo, con un menor rango de error pues solo mostraría los resultados de las opciones escogidas.
4. **El QUO**: existiendo una base de datos relacional, el quo se vuelve hasta cierto punto innecesario, puesto que al finalizar al cliente, el cotizador puede seleccionar un estatus de los posibles y guardarlo en ese status (propuesta enviada, crédito declinado, crédito aprobado, etc...).
5. **Usuarios**:Este proceso también facilita el seguimiento de los usuarios (trabajadores) que han tenido contacto especifico con la información de un cliente y se puede seguir el proceso debidamente. Ligando el cliente a todos los usuarios que hayan participado en el proceso. Es decir Usuario::Consultor sube la información y es recibida por Usuario::Cotizador1 quien ese día solo llega hasta el crédito aprobado, al día siguiente Usuario::Cotizador2 recibe la información y lleva la propuesta hasta el cierre.

## Propuesta de base de datos:

Usando postgreSQL la base de datos estaria centrada en el cliente segun el siguiente diagrama:


## Usuarios y autorizacion:

Los usuarios estarian identificados por un atributo llamado rol: de diferentes niveles y para diferentes funciones.

rol:consultor para enviar clientes.
rol:Cotizador para procesarlos y ver la info completa de los mismos y editar ciertos parametros.

Tambien hacer falta un nivel de autorizacion del usuario, para diferenciar a gerentes de trabajadores rasos.


Para agregar a los otros miembros del equipo y las otras funciones debo conocer un poco mejor la empresa y como estamos funcionando.
