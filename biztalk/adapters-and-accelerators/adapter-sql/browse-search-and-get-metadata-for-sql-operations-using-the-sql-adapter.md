---
title: Examinar, buscar y obtener metadatos para operaciones de SQL mediante el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdd5ca6f-30ff-4d32-a656-bbd54b9d072e
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30f76d18f79206fff217ab080c9e2b052aa4f73b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971101"
---
# <a name="browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter"></a>Examinar, buscar y obtener metadatos para operaciones de SQL mediante el adaptador de SQL
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Si se utilizan [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes, puede:  
  
- Buscar operaciones para que se va a recuperar los metadatos.  
  
- Búsqueda de operaciones que se va a recuperar los metadatos.  
  
- Agregar esquemas de mensaje para operaciones seleccionadas y el puerto de los archivos de configuración de enlace a un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
- Agregar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para las operaciones seleccionadas y un archivo de configuración (app.config) a un proyecto de programación que no sean de BizTalk cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes esencialmente la misma interfaz al examinar y buscar las operaciones, por lo que los tres componentes se tratan en los mismos temas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a SQL Server antes de que puede examinar, buscar o recuperar metadatos para operaciones de destino. Para obtener información acerca de cómo conectarse a SQL Server cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectar con SQL Server en Visual Studio mediante el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).  
  
## <a name="browsing-for-operations"></a>Para las operaciones de exploración  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar operaciones entrantes y salientes que se pueden realizar en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
### <a name="outbound-operations"></a>Operaciones salientes  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes a realizar las siguientes operaciones de salida.  
  
- INSERT, Select, Update y eliminar operaciones en tablas y vistas.  
  
- < Nombre_columna > conjunto de operaciones en tablas y vistas. Esta operación se expone en tablas que tengan columnas varchar (max), nvarchar (max) o varbinary (max). Estas operaciones habilitar el streaming de objetos grandes.  
  
- Procedimientos almacenados, tanto débil como fuertemente tipadas como las operaciones.  
  
- Escalares y tabla de funciones con valores como las operaciones.  
  
  El adaptador también expone las operaciones de salida genéricas como **ExecuteReader**, **ExecuteScalar**, y **ExecuteNonQuery** en el nivel raíz.  
  
### <a name="inbound-operations"></a>Operaciones de entrada  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes a realizar las siguientes operaciones de entrada.  
  
-   **Sondeo** operación para recibir mensajes de cambio de datos basados en sondeos de SQL Server. Los mensajes recibidos para esta operación no están fuertemente tipados.  
  
-   **TypedPolling** operación para recibir mensajes de cambio de datos basados en sondeos de SQL Server. Los mensajes recibidos para esta operación están fuertemente tipados.  
  
-   **Notificación** operación para recibir notificaciones de consulta de SQL Server.  
  
> [!NOTE]
>  El adaptador también admite un **XmlPolling** operación para habilitar el sondeo en base de datos de SQL Server mediante instrucciones SELECT y procedimientos almacenados que contengan una cláusula FOR XML de entrada. Sin embargo, el adaptador no expone una operación de entrada específica para este. Para obtener más información sobre XmlPolling, consulte [recibir mensajes de sondeo mediante las instrucciones SELECT con la cláusula FOR XML de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).  
  
 Para obtener más información acerca de estas operaciones, consulte [conectar a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md).  
  
> [!NOTE]
>  Mediante el uso de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], puede examinar la categoría y el funcionamiento de los nodos mediante una interfaz de Windows.  
  
 Para obtener más información sobre los metadatos de exploración, consulte [obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
##### <a name="to-browse-outbound-operations-on-sql-server"></a>Para examinar las operaciones salientes en SQL Server  
  
1. Conectarse a SQL Server mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con SQL Server en Visual Studio mediante el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista para seleccionar las operaciones salientes **Client (Outbound operations)**.  
  
3. El **seleccionar una categoría** cuadro muestran los artefactos disponibles en la base de datos de SQL Server se conecta a. Haga clic en un artefacto para ver las operaciones disponibles para ese artefacto en el **operaciones y categorías disponibles** cuadro.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto, mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **empleado** nodo de la tabla, mantener el foco en el **tablas** nodo y, a continuación, escriba `Employee`.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/), y se muestran los nodos de categoría general disponibles en el nodo raíz en el **operaciones y categorías disponibles** cuadro.  
  
    ![Las operaciones y categorías disponibles a nivel de raíz](../../adapters-and-accelerators/adapter-sql/media/3eef7b99-da8e-4b98-8b14-8e48fd7b3801.gif "3eef7b99-da8e-4b98-8b14-8e48fd7b3801")  
  
   > [!NOTE]
   >  Las operaciones de SQL Server estándar, como ExecuteNonQuery, ExecuteReader y ExecuteScalar también están disponibles en el nivel raíz. Para obtener más información acerca de estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
4. Para ver los procedimientos disponibles en la base de datos de SQL Server, haga clic en el **procedimientos** nodo. En la ilustración siguiente, el **procedimientos** nodo está seleccionado en el **seleccionar una categoría** cuadro y los procedimientos correspondientes se muestran en el **operaciones y categorías disponibles cuadro**.  
  
    ![Examinar procedimientos en el servidor SQL Server](../../adapters-and-accelerators/adapter-sql/media/e3b1a070-4077-4e4d-bfc7-558df9b8b9d5.gif "e3b1a070-4077-4e4d-bfc7-558df9b8b9d5")  
  
   > [!NOTE]
   >  El mismo conjunto de procedimientos que aparecen en la **procedimientos** nodo también están disponibles en el **Strongly-Typed procedimientos** nodo. La diferencia radica en la forma en que se genera el esquema. Para obtener un procedimiento en el **procedimiento** nodo, el esquema es débilmente tipados. Sin embargo, para un procedimiento en el **Strongly-Typed procedimiento** nodo, el esquema está fuertemente tipado. Esquema fuertemente tipado es útil si desea asignar el esquema de una operación para otra operación con el asignador de BizTalk porque el esquema está disponible en tiempo de diseño al crear el proyecto de BizTalk. Para los procedimientos débilmente tipada, se recibe el esquema para el procedimiento en tiempo de ejecución como parte del mensaje de respuesta.  
  
5. Para ver las tablas de la base de datos de SQL Server, haga clic en el **tablas** nodo. Como alternativa, expanda el **tablas** nodo.  
  
6. Para ver las operaciones admitidas en la tabla, haga clic en un nombre de tabla.  
  
    La siguiente ilustración muestra una lista de tablas en el **seleccionar una categoría** cuadro. El **operaciones y categorías disponibles** cuadro enumera las operaciones admitidas de una tabla seleccionada.  
  
    ![Examinar tablas en una base de datos de SQL Server](../../adapters-and-accelerators/adapter-sql/media/3966f3b9-85a0-4354-8ed4-da5ae74c9885.gif "3966f3b9-85a0-4354-8ed4-da5ae74c9885")  
  
   > [!NOTE]
   >  Si una tabla de SQL Server contiene columnas de tipo varchar (max), nvarchar (max) y varbinary (max), el adaptador también expone una operación específica para actualizar los datos de esa columna. El nombre de esta operación se establece < nombre_columna >. Por ejemplo, si la tabla tiene una columna "Job_Description" de tipo varchar (max), el nombre de la operación es "SetJob_Description".  
  
7. Para ver las vistas en la base de datos de SQL Server, haga clic en el **vistas** nodo. Como alternativa, expanda el **vistas** nodo.  
  
8. Para ver las operaciones admitidas en la vista, haga clic en un nombre de vista.  
  
    La siguiente ilustración muestra una lista de vistas en el **seleccionar una categoría** cuadro. El **operaciones y categorías disponibles** cuadro enumera las operaciones admitidas para obtener una vista seleccionada.  
  
    ![Examinar vistas en una base de datos de SQL Server](../../adapters-and-accelerators/adapter-sql/media/67362fb2-35fb-4afb-8ff6-e519b26bd187.gif "67362fb2-35fb-4afb-8ff6-e519b26bd187")  
  
   > [!NOTE]
   >  Si una vista contiene columnas de tipo varchar (max), nvarchar (max) y varbinary (max), el adaptador también expone una operación específica para actualizar los datos de esa columna. El nombre de esta operación se establece < nombre_columna >. Por ejemplo, si la tabla tiene una columna "Job_Description" de tipo varchar (max), el nombre de la operación es "SetJob_Description".  
  
9. Para ver la lista de las funciones escalares definidas en la base de datos de SQL Server en el **operaciones y categorías disponibles** cuadro, haga clic en el **funciones escalares** nodo.  
  
     En la ilustración siguiente, el **funciones escalares** nodo está seleccionado en el **seleccionar una categoría** cuadro y las funciones correspondientes se muestran en el **operaciones y categorías disponibles**  cuadro.  
  
     ![Examinar funciones escalares en SQL Server](../../adapters-and-accelerators/adapter-sql/media/78b9f720-2cb2-44a8-b8cc-49e4fb608a1f.gif "78b9f720-2cb2-44a8-b8cc-49e4fb608a1f")  
  
10. Para ver la lista de tabla con valores de las funciones definidas en la base de datos de SQL Server en el **operaciones y categorías disponibles** cuadro, haga clic en el **funciones con valores de tabla** nodo.  
  
     En la ilustración siguiente, el **funciones con valores de tabla** nodo está seleccionado en el **seleccionar una categoría** cuadro y las funciones correspondientes se muestran en el **categorías disponibles y las operaciones** cuadro.  
  
     ![Examinar las funciones con valores de tabla en SQL Server](../../adapters-and-accelerators/adapter-sql/media/b007059f-280e-40d7-9553-eca4216296f4.gif "b007059f-280e-40d7-9553-eca4216296f4")  
  
##### <a name="to-browse-inbound-operations-on-sql-server"></a>Para buscar operaciones entrantes en SQL Server  
  
1. Conectarse a SQL Server mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con SQL Server en Visual Studio mediante el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista para las operaciones de entrada, seleccione **(operaciones de entrada) de servicio**.  
  
3. Todas las operaciones entrantes admitidas por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] están disponibles en el nodo raíz. Haga clic en el nodo raíz (/) para ver las operaciones de entrada disponibles.  
  
    ![Operaciones entrantes admitidas por el adaptador](../../adapters-and-accelerators/adapter-sql/media/133732c0-ca8f-4e57-8a70-ba4fb561a37b.gif "133732c0-ca8f-4e57-8a70-ba4fb561a37b")  
  
## <a name="searching-for-operations"></a>Búsqueda de operaciones  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar artefactos específicos en la base de datos de SQL Server. Al buscar metadatos de SQL Server, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
- Admite caracteres comodín y escape en la expresión de búsqueda.  
  
- Permite la búsqueda se encuentra inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una tabla, debe buscar en \Table. No se admite la búsqueda de varios nivel.  
  
  En la tabla siguiente se enumera los caracteres especiales que se pueden usar para la búsqueda de artefactos y su interpretación por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
|Carácter especial|Interpretación|Ejemplo|  
|-----------------------|--------------------|-------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter|Coincide con "A_" AB, CA, AD.|  
|%|Coincide con cero o más caracteres|"%" Coincide con A, AB AC.|  
|[ ]|-Establece secuencias de escape el significado especial de % y _<br />-Especifica un intervalo o conjunto de caracteres que se va a estar presente|-% [%] coincide con todos los nombres que incluyen un símbolo %.<br />-[a-f] coincide con todos los nombres que tienen caracteres entre (e incluido) 'a' y 'f'.<br />-[abc] coincide con todos los nombres que tienen caracteres 'a', 'b' y 'c'.|  
|[^]|Especifica un intervalo o conjunto de caracteres que no sean presente|-[^ a-f] coincide con todos los nombres que no tienen caracteres entre (e incluyendo) 'a' y 'f'.<br />-[^ abc] coincide con todos los nombres que no tienen caracteres 'a', 'b' y 'c'.|  
  
> [!NOTE]
>  Carácter de escape es un carácter que se coloca delante de un carácter comodín para indicar que el carácter comodín debe interpretarse como un carácter normal y no como un carácter comodín.  
  
 Para obtener más información, consulte [obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
 Buscar metadatos en SQL Server mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], realice los pasos siguientes.  
  
#### <a name="to-search-metadata-in-sql-server"></a>Buscar metadatos en SQL Server  
  
1. Conectarse a SQL Server mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con SQL Server en Visual Studio mediante el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista, seleccione el tipo de contrato en función de si está buscando operaciones de entrada o salidas.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el nodo de categoría en la que desea buscar un artefacto específico. Por ejemplo, para buscar una tabla, haga clic en el **tablas** nodo.  
  
4. En el **búsqueda en la categoría** , escriba una expresión de búsqueda para buscar un artefacto específico. Por ejemplo, para buscar las tablas que tienen "Cliente" en su nombre, escriba `%Customer%`.  
  
   > [!NOTE]
   >  La cadena de búsqueda distingue mayúsculas de minúsculas.  
  
5. Para iniciar la búsqueda, haga clic en el botón con el icono de flecha derecha. Una vez completada la búsqueda, el **operaciones y categorías disponibles** cuadro muestran los artefactos que cumplen los criterios de búsqueda.  
  
    La siguiente ilustración muestra las tablas de SQL Server que contienen a "Cliente" en su nombre.  
  
    ![Buscar metadatos en SQL Server](../../adapters-and-accelerators/adapter-sql/media/62c24ed3-f4e5-47de-8e8d-35af96e6c5ec.gif "62c24ed3-f4e5-47de-8e8d-35af96e6c5ec")  
  
## <a name="generating-schema-for-biztalk-projects"></a>Generar el esquema para los proyectos de BizTalk  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para los artefactos de SQL Server seleccionados. Después de examinar y buscar los artefactos que desea invocar, puede generar el esquema para aquellos artefactos y enviar mensajes, que se ajuste al esquema, para SQL Server.  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de la categoría, por ejemplo, puede seleccionar una tabla completa (para generar el esquema para todas las operaciones en la tabla) o seleccione operaciones específicas en una tabla (por ejemplo, Insert y Delete) a Genere el esquema solo esas operaciones en una tabla. Para obtener más información acerca de los nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).  
  
#### <a name="to-generate-schema-for-sql-server-artifacts"></a>Para generar el esquema para los artefactos de SQL Server  
  
1. Conectarse a SQL Server mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Consulte [conectar con SQL Server en Visual Studio mediante el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
   > [!IMPORTANT]
   >  Para generar el esquema para realizar operaciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Debe establecer esta propiedad de enlace al establecer una conexión a la base de datos de SQL Server.  
  
2. Desde el **seleccione el tipo de contrato** lista, seleccione el tipo de contrato en función de si va a generar el esquema para las operaciones de entrada o salidas.  
  
3. Haga clic en el nodo de categoría para el que desea generar los metadatos. Por ejemplo, si desea generar los metadatos para una tabla, haga clic en **tablas**.  
  
4. Expanda el nodo de categoría y seleccione el elemento específico dentro de ese nodo para el que desea generar los metadatos. Por ejemplo, para generar metadatos para operaciones en la tabla "CustomerTable", expanda el **tablas** nodo y, a continuación, haga clic en **CustomerTable**.  
  
5. En el **operaciones y categorías disponibles** , seleccione las operaciones que desee realizar en SQL Server y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas aparecen en la **agregar categorías y operaciones** cuadro. Por ejemplo, para realizar operaciones de inserción y seleccionadas en la tabla "CustomerTable", haga clic en los nombres de operación y, a continuación, haga clic en **agregar**.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que enumera las operaciones seleccionadas.  
  
    ![Recuperar metadatos desde SQL Server](../../adapters-and-accelerators/adapter-sql/media/a6a95291-f6ed-46d1-bacc-2dfc27638117.gif "a6a95291-f6ed-46d1-bacc-2dfc27638117")  
  
    Si desea generar el esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos "CT1". Después de generar el esquema para "Op1" cerrar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar esquemas para otra operación "Op2". Suponga que "Op2" también contiene un parámetro de tipo de datos "CT1". Después de salir el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, recibirá errores de compilación porque se define el tipo de datos complejos "CT1" dos veces en distintos archivos XSD. En tales situaciones, se recomienda lo siguiente:  
  
   - Genere el esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejos "CT1".  
  
   - Si desea generar el esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar el **generar tipos de esquema únicos** casilla para que los archivos XSD generados contienen espacios de nombres únicos para el "CT1" de tipo de datos complejos.  
  
6. Haga clic en **Aceptar**. El archivo de esquema se guarda con la extensión .xsd en la misma ubicación que el proyecto de BizTalk.  
  
   > [!NOTE]
   >  Si usas el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar metadatos para artefactos de SQL Server, de forma predeterminada, los archivos se crean con una convención de nomenclatura específica. El WSDL generado contiene un **fileNameHint** etiqueta de anotación que incluya el nombre que se debe asignar al archivo XSD. Por ejemplo, una sugerencia de nombre de archivo para un archivo de esquema para la operación de tabla sigue la convención TableOperation. \<esquema\>.\< TableName\>. Si desea personalizar el nombre del archivo XSD generado, puede proporcionar un prefijo en el **prefijo de nombre de archivo** cuadro. Por último, el nombre de un archivo XSD se ha llegado al como prefijo del nombre de archivo fileNameHint + entero único (si es necesario, para asegurarse de que el nombre de archivo es exclusivo).  
   > 
   > [!NOTE]
   >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace que especificó al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] set de la consola de administración para crear un puerto personalizado de WCF o BizTalk SQL puerto del adaptador con el URI de conexión, propiedades de enlace y la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
    Ha generado correctamente los metadatos para artefactos de SQL Server. Puede utilizar los metadatos para enviar mensajes a SQL Server para realizar operaciones específicas. Consulte [aplicaciones de desarrollo de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md) para obtener más información acerca de cómo realizar estas operaciones.  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>Generar un cliente de WCF o contrato de servicio WCF usando la Add Adapter Service Reference complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para las operaciones de salida o código de servicio WCF para las operaciones de entrada.  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-sql-server-operations"></a>Para generar el contrato de servicio o la clase de cliente WCF para las operaciones de SQL Server  
  
1. En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar las operaciones de entrada o salidas.  
  
2. Examine o busque por categorías (por ejemplo, una tabla de base de datos) o para las operaciones específicas para el que desea generar un cliente WCF (o contrato de servicio WCF).   
   Por ejemplo, para buscar las operaciones en la tabla de empleados, en el **seleccionar una categoría** cuadro:  
  
   1.  Expanda el nodo raíz (**/**) para ver las categorías en la que se exponen las operaciones de una base de datos de SQL Server.  
  
   2.  En el nodo raíz, expanda el **tablas** nodo para ver las tablas disponibles.  
  
3. Haga clic en el **empleado** nodo de la tabla y en el **operaciones y categorías disponibles** , seleccione las operaciones o categorías para el que desea generar un cliente de WCF (o contrato de servicio WCF) y, a continuación, Haga clic en **agregar**. Las operaciones seleccionadas aparecen en la **agregar categorías y operaciones** cuadro.  
  
    La siguiente ilustración muestra el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] con la inserción y las operaciones Select para la tabla Employee seleccionado.  
  
    ![Generar el contrato de servicio o cliente WCF](../../adapters-and-accelerators/adapter-sql/media/sql-adap-add-adap-serv-ref.gif "sql_adap_add_adap_serv_ref")  
  
   > [!IMPORTANT]
   >  Según las operaciones de salida (o categorías) que usted seleccione, más de un WCF pueden generarse clases de cliente. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
4. Para la mayoría de los escenarios son suficientes; las opciones de serialización predeterminado Sin embargo, si es necesario, puede controlar varios aspectos sobre el código generado y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
   1. Haga clic en **opciones avanzadas** para abrir el **opciones avanzadas** cuadro.  
  
   2. En el **opciones avanzadas** cuadro bajo **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si los métodos asincrónicos se generan para el cliente de WCF o deshabilitar la generación de un archivo de configuración.  
  
   3. En **serializador** selecciona el serializador que se debe usar.  
  
      La siguiente ilustración muestra el **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y ninguna otra opción que se ha seleccionado).  
  
      ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      Las opciones que se pueden configurar en el **opciones avanzadas** cuadro son equivalentes a algunas de las opciones disponibles al utilizar ServiceModel Metadata Utility Tool (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx). 
  
5. Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda la clase de cliente WCF (o la interfaz de servicio WCF) y código auxiliar para las operaciones y categorías que ha seleccionado en el directorio del proyecto. De forma predeterminada, también se guarda un archivo de configuración. Se generan archivos ligeramente diferentes para las operaciones de entrada y salidas; Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
   Puede seleccionar cualquier nodo que aparece en el **operaciones y categorías disponibles** cuadro. Si selecciona un nodo de categoría, a continuación, se seleccionarán todas las operaciones disponibles en ese nodo y sus nodos secundarios. Por ejemplo, para generar a un cliente WCF para todas las operaciones que aparece para la tabla Employee, puede seleccionar el nodo de empleado.  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)