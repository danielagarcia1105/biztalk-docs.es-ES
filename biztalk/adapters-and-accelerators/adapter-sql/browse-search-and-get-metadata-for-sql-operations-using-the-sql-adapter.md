---
title: Examinar, buscar y obtener los metadatos de las operaciones de SQL con el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd5ca6f-30ff-4d32-a656-bbd54b9d072e
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8d82a69b342c278e7cb17de8759d4986a71cd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter"></a>Examinar, buscar y obtener los metadatos de las operaciones de SQL con el adaptador de SQL
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Mediante el uso de estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes, puede:  
  
-   Buscar operaciones para el que se va a recuperar los metadatos.  
  
-   Buscar operaciones para el que se va a recuperar los metadatos.  
  
-   Agregar esquemas de mensaje para las operaciones seleccionadas y el puerto de los archivos de configuración de enlace para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
-   Agregar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para operaciones seleccionadas y un archivo de configuración (app.config) a un proyecto de programación de BizTalk no cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes básicamente la misma interfaz al examinar y buscar las operaciones, por lo que los tres componentes se tratan en los temas de la mismos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a SQL Server para poder examinar, buscar o recuperar los metadatos para las operaciones de destino. Para obtener información acerca de cómo conectarse a SQL Server cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectar con SQL Server en Visual Studio usando el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).  
  
## <a name="browsing-for-operations"></a>Búsqueda de operaciones  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar operaciones entrantes y salientes que se pueden realizar en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
### <a name="outbound-operations"></a>Operaciones de salida  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes realizar las siguientes operaciones de salida.  
  
-   INSERT, Select, Update y operaciones Delete en tablas y vistas.  
  
-   Conjunto < column_name > operaciones en tablas y vistas. Esta operación se expone en tablas que tengan columnas varchar (max), nvarchar (max) o varbinary (max). Estas operaciones habilite el streaming de objetos grandes.  
  
-   Procedimientos almacenados, débilmente y fuertemente tipadas como operaciones.  
  
-   Escalar y tabla de funciones con valores como operaciones.  
  
 El adaptador también expone las operaciones de salida genéricas como **ExecuteReader**, **ExecuteScalar**, y **ExecuteNonQuery** en el nivel raíz.  
  
### <a name="inbound-operations"></a>Operaciones de entrada  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes realizar las siguientes operaciones de entrada.  
  
-   **Sondeo** operación para recibir mensajes de cambio de datos basado en sondeo de SQL Server. Los mensajes recibidos para esta operación no están fuertemente tipados.  
  
-   **TypedPolling** operación para recibir mensajes de cambio de datos basado en sondeo de SQL Server. Los mensajes recibidos para esta operación tienen establecimiento inflexible de tipos.  
  
-   **Notificación** operación para recibir las notificaciones de consulta de SQL Server.  
  
> [!NOTE]
>  El adaptador también admite un **XmlPolling** operación para habilitar el sondeo en base de datos de SQL Server utilizando las instrucciones SELECT y procedimientos almacenados que contienen una cláusula FOR XML de entrada. Sin embargo, el adaptador no expone una operación de entrada específica para este. Para obtener más información sobre XmlPolling, consulte [recibir mensajes de sondeo mediante las instrucciones SELECT con la cláusula FOR XML de SQL mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).  
  
 Para obtener más información acerca de estas operaciones, vea [conectar a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md).  
  
> [!NOTE]
>  Mediante el uso de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], puede examinar los nodos de categoría y operación mediante una interfaz de Windows.  
  
 Para obtener más información acerca de los metadatos de exploración, vea [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
##### <a name="to-browse-outbound-operations-on-sql-server"></a>Para examinar las operaciones salientes en SQL Server  
  
1.  Conectarse a SQL Server mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectar con SQL Server en Visual Studio usando el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista para seleccionar las operaciones salientes **Client (Outbound operations)**.  
  
3.  El **seleccione una categoría de** cuadro muestra los artefactos disponibles en la base de datos de SQL Server se conecta a. Haga clic en un artefacto para ver las operaciones disponibles para ese artefacto en la **categorías y operaciones disponibles** cuadro.  
  
    > [!TIP]
    >  Puede ir directamente a la categoría "inmediata" nodos de subcategoría en el árbol, puede escribir el nombre del artefacto, mientras el foco está en la vista de árbol en el **seleccione una categoría de** cuadro. Por ejemplo, para saltar a la **empleado** nodo de la tabla, mantener el foco en el **tablas** nodo y, a continuación, escriba `Employee`.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/) y los nodos de categoría general disponibles bajo el nodo raíz se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Operaciones y categorías disponibles en el nivel de raíz](../../adapters-and-accelerators/adapter-sql/media/3eef7b99-da8e-4b98-8b14-8e48fd7b3801.gif "3eef7b99-da8e-4b98-8b14-8e48fd7b3801")  
  
    > [!NOTE]
    >  Las operaciones de SQL Server estándar como ExecuteReader, ExecuteScalar y ExecuteNonQuery también están disponibles en el nivel raíz. Para obtener más información acerca de estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
4.  Para ver los procedimientos disponibles en la base de datos de SQL Server, haga clic en el **procedimientos** nodo. En la ilustración siguiente, la **procedimientos** nodo está seleccionado en el **seleccione una categoría de** cuadro y los procedimientos correspondientes se muestran en la **categorías y operaciones disponibles cuadro**.  
  
     ![Examinar procedimientos en SQL Server](../../adapters-and-accelerators/adapter-sql/media/e3b1a070-4077-4e4d-bfc7-558df9b8b9d5.gif "e3b1a070-4077-4e4d-bfc7-558df9b8b9d5")  
  
    > [!NOTE]
    >  El mismo conjunto de procedimientos que aparecen en la **procedimientos** nodo también están disponibles en la **Strongly-Typed procedimientos** nodo. La diferencia radica en la forma en que se genera el esquema. Para obtener un procedimiento en el **procedimiento** nodo, el esquema es débilmente tipada. Sin embargo, para un procedimiento en el **Strongly-Typed procedimiento** nodo, el esquema está fuertemente tipado. Esquema fuertemente tipado es útil si desea asignar el esquema de una operación para otra operación con el asignador de BizTalk porque el esquema está disponible en tiempo de diseño al crear el proyecto de BizTalk. Para conocer los procedimientos débilmente tipada, el esquema para el procedimiento se recibe en tiempo de ejecución como parte del mensaje de respuesta.  
  
5.  Para ver las tablas de la base de datos de SQL Server, haga clic en el **tablas** nodo. O bien, expanda la **tablas** nodo.  
  
6.  Para ver las operaciones admitidas en la tabla, haga clic en un nombre de tabla.  
  
     La siguiente ilustración muestra una lista de tablas en el **seleccione una categoría de** cuadro. El **categorías y operaciones disponibles** cuadro enumera las operaciones compatibles para una tabla seleccionada.  
  
     ![Examinar tablas en una base de datos de SQL Server](../../adapters-and-accelerators/adapter-sql/media/3966f3b9-85a0-4354-8ed4-da5ae74c9885.gif "3966f3b9-85a0-4354-8ed4-da5ae74c9885")  
  
    > [!NOTE]
    >  Si una tabla de SQL Server contiene columnas de tipo varchar (max), nvarchar (max) y varbinary (max), el adaptador también expone una operación específica para actualizar los datos de esa columna. El nombre de esta operación se establece < column_name >. Por ejemplo, si la tabla tiene una columna "Job_Description" de tipo varchar (max), el nombre de la operación es "SetJob_Description".  
  
7.  Para ver las vistas en la base de datos de SQL Server, haga clic en el **vistas** nodo. O bien, expanda la **vistas** nodo.  
  
8.  Para ver las operaciones admitidas en la vista, haga clic en un nombre de vista.  
  
     La siguiente ilustración muestra una lista de vistas en el **seleccione una categoría de** cuadro. El **categorías y operaciones disponibles** cuadro enumera las operaciones admitidas para obtener una vista seleccionada.  
  
     ![Examinar vistas en una base de datos de SQL Server](../../adapters-and-accelerators/adapter-sql/media/67362fb2-35fb-4afb-8ff6-e519b26bd187.gif "67362fb2-35fb-4afb-8ff6-e519b26bd187")  
  
    > [!NOTE]
    >  Si una vista contiene columnas de tipo varchar (max), nvarchar (max) y varbinary (max), el adaptador también expone una operación específica para actualizar los datos de esa columna. El nombre de esta operación se establece < column_name >. Por ejemplo, si la tabla tiene una columna "Job_Description" de tipo varchar (max), el nombre de la operación es "SetJob_Description".  
  
9. Para ver la lista de funciones escalares definidas en la base de datos de SQL Server en el **categorías y operaciones disponibles** cuadro, haga clic en el **funciones escalares** nodo.  
  
     En la ilustración siguiente, la **funciones escalares** nodo está seleccionado en el **seleccione una categoría de** cuadro y las funciones correspondientes se muestran en la **categorías y operaciones disponibles**  cuadro.  
  
     ![Examinar funciones escalares en SQL Server](../../adapters-and-accelerators/adapter-sql/media/78b9f720-2cb2-44a8-b8cc-49e4fb608a1f.gif "78b9f720-2cb2-44a8-b8cc-49e4fb608a1f")  
  
10. Para ver la lista de tabla con valores de las funciones definidas en la base de datos de SQL Server en el **categorías y operaciones disponibles** cuadro, haga clic en el **funciones con valores de tabla** nodo.  
  
     En la ilustración siguiente, la **funciones con valores de tabla** nodo está seleccionado en el **seleccione una categoría de** cuadro y las funciones correspondientes se muestran en la **categorías disponibles y operaciones** cuadro.  
  
     ![Examinar las funciones con valores de tabla en SQL Server](../../adapters-and-accelerators/adapter-sql/media/b007059f-280e-40d7-9553-eca4216296f4.gif "b007059f-280e-40d7-9553-eca4216296f4")  
  
##### <a name="to-browse-inbound-operations-on-sql-server"></a>Para buscar operaciones entrantes en SQL Server  
  
1.  Conectarse a SQL Server mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectar con SQL Server en Visual Studio usando el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista para las operaciones de entrada, seleccione **(operaciones de entrada) de servicio**.  
  
3.  Todas las operaciones entrantes admitidas por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] están disponibles en el nodo raíz. Haga clic en el nodo raíz (/) para ver las operaciones de entrada disponibles.  
  
     ![Operaciones admitidas por el adaptador de entrada](../../adapters-and-accelerators/adapter-sql/media/133732c0-ca8f-4e57-8a70-ba4fb561a37b.gif "133732c0-ca8f-4e57-8a70-ba4fb561a37b")  
  
## <a name="searching-for-operations"></a>Búsqueda de operaciones  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar artefactos específicos en la base de datos de SQL Server. Al buscar los metadatos de SQL Server, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
-   Admite caracteres comodín y escape en la expresión de búsqueda.  
  
-   Permite la búsqueda inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una tabla, debe buscar en \Table. No se admite la búsqueda de varios nivel.  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para la búsqueda de artefactos y su interpretación por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
|Carácter especial|Interpretación|Ejemplo|  
|-----------------------|--------------------|-------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter|Coincide con "A_" AB, CA, AD.|  
|%|Coincide con cero o más caracteres|"%" Coincide con A, AB CA.|  
|[ ]|-Antepone el significado especial de % y _<br />-Especifica un intervalo o un conjunto de caracteres que se va a estar presente|-% [%] coincide con todos los nombres que incluyen un símbolo %.<br />-[a-f] coincide con todos los nombres que tienen caracteres entre (e incluyendo) 'a' y 'f'.<br />-[abc] coincide con todos los nombres que tienen caracteres 'a', 'b' y 'c'.|  
|[^]|Especifica un intervalo o conjunto de caracteres no presente|-[^ a-f] coincide con todos los nombres que no tienen caracteres entre (e incluyendo) 'a' y 'f'.<br />-[^ abc] coincide con todos los nombres que no tienen caracteres 'a', 'b' y 'c'.|  
  
> [!NOTE]
>  Carácter de escape es un carácter que se coloca delante de un carácter comodín para indicar que el carácter comodín debe interpretarse como un carácter normal y no como un carácter comodín.  
  
 Para obtener más información, consulte [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
 Buscar metadatos en SQL Server mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], realice los pasos siguientes.  
  
#### <a name="to-search-metadata-in-sql-server"></a>Para buscar metadatos en SQL Server  
  
1.  Conectarse a SQL Server mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectar con SQL Server en Visual Studio usando el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** , seleccione el tipo de contrato en función de si está buscando las operaciones de entrada o salidas.  
  
3.  En el **seleccione una categoría de** cuadro, haga clic en el nodo de categoría en la que desea buscar un artefacto específico. Por ejemplo, para buscar una tabla, haga clic en el **tablas** nodo.  
  
4.  En el **búsqueda en la categoría** , escriba una expresión de búsqueda para buscar un artefacto específico. Por ejemplo, para buscar las tablas que tienen "Cliente" en su nombre, escriba `%Customer%`.  
  
    > [!NOTE]
    >  La cadena de búsqueda distingue mayúsculas de minúsculas.  
  
5.  Para iniciar la búsqueda, haga clic en el botón con el icono de flecha derecha. Una vez completada, la búsqueda del **categorías y operaciones disponibles** cuadro muestra los artefactos que cumplen los criterios de búsqueda.  
  
     La siguiente ilustración muestra las tablas de SQL Server que contienen a "Cliente" en su nombre.  
  
     ![Buscar metadatos en SQL Server](../../adapters-and-accelerators/adapter-sql/media/62c24ed3-f4e5-47de-8e8d-35af96e6c5ec.gif "62c24ed3-f4e5-47de-8e8d-35af96e6c5ec")  
  
## <a name="generating-schema-for-biztalk-projects"></a>Generar el esquema para los proyectos de BizTalk  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para los artefactos de SQL Server seleccionados. Una vez examinar y buscar los artefactos que desea invocar, puede generar esquema para los artefactos y enviar mensajes, que se ajuste al esquema, para SQL Server.  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de esa categoría, por ejemplo, puede seleccionar una tabla completa (para generar esquemas para todas las operaciones en la tabla) o seleccione operaciones específicas en una tabla (por ejemplo, Insert y Delete) a Genere el esquema para solo esas operaciones en una tabla. Para obtener más información acerca de los nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).  
  
#### <a name="to-generate-schema-for-sql-server-artifacts"></a>Para generar el esquema para los artefactos de SQL Server  
  
1.  Conectarse a SQL Server mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Vea [conectar con SQL Server en Visual Studio usando el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md) para obtener instrucciones.  
  
    > [!IMPORTANT]
    >  Para generar el esquema para realizar operaciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Debe establecer esta propiedad de enlace al establecer una conexión a la base de datos de SQL Server.  
  
2.  Desde el **seleccione el tipo de contrato** , seleccione el tipo de contrato en función de si va a generar esquema para las operaciones de entrada o salidas.  
  
3.  Haga clic en el nodo de categoría para la que desea generar los metadatos. Por ejemplo, si desea generar metadatos para una tabla, haga clic en **tablas**.  
  
4.  Expanda el nodo de categoría y seleccione el elemento específico en ese nodo para el que desea generar los metadatos. Por ejemplo, para generar metadatos para las operaciones en la tabla "CustomerTable", expanda la **tablas** nodo y, a continuación, haga clic en **CustomerTable**.  
  
5.  En el **categorías y operaciones disponibles** , seleccione las operaciones que desea realizar en SQL Server y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas se muestran en la **agregar categorías y operaciones** cuadro. Por ejemplo, para realizar operaciones de inserción y seleccionadas en la tabla "CustomerTable", haga clic en los nombres de operación y, a continuación, haga clic en **agregar**.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que enumeran las operaciones seleccionadas.  
  
     ![Recuperar metadatos desde SQL Server](../../adapters-and-accelerators/adapter-sql/media/a6a95291-f6ed-46d1-bacc-2dfc27638117.gif "a6a95291-f6ed-46d1-bacc-2dfc27638117")  
  
     Si desea generar esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos "CT1". Después de generar el esquema para "Op1" cerrar la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar el esquema para otra operación "Op2". Supongamos que "Op2" también contiene un parámetro de tipo de datos "CT1". Después de salir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, se producirán errores de compilación porque el tipo de datos complejo "CT1" se define dos veces en distintos archivos XSD. En estas situaciones, se recomienda lo siguiente:  
  
    -   Generar esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejo "CT1".  
  
    -   Si desea generar esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar la **generar tipos de esquema únicos** casilla para que los archivos XSD generados contienen espacios de nombres únicos para el "CT1" de tipo de datos complejos.  
  
6.  Haga clic en **Aceptar**. El archivo de esquema se guarda con una extensión .xsd en la misma ubicación que el proyecto de BizTalk.  
  
    > [!NOTE]
    >  Si usas el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar metadatos para los artefactos de SQL Server, de forma predeterminada, los archivos se crean con una convención de nomenclatura específica. El WSDL generado contiene un **fileNameHint** etiqueta de anotación que incluye el nombre que se debe asignar al archivo XSD. Por ejemplo, una sugerencia de nombre de archivo para un archivo de esquema para la operación de tabla sigue la convención de TableOperation. \<esquema >. \<NombreDeTabla >. Si desea personalizar el nombre del archivo XSD generado, puede proporcionar un prefijo en el **prefijo de nombre de archivo** cuadro. Por último, el nombre de un archivo XSD se llegó al como prefijo de nombre de archivo + fileNameHint + entero único (si es necesario, para asegurarse de que el nombre de archivo es único).  
  
    > [!NOTE]
    >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace especificado al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] set de la consola de administración para crear un puerto personalizado de WCF o BizTalk SQL puerto del adaptador con el URI de conexión, propiedades de enlace y la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
     Ha generado correctamente los metadatos para los artefactos de SQL Server. Puede utilizar los metadatos para enviar mensajes a SQL Server para realizar operaciones específicas. Vea [aplicaciones de BizTalk de desarrollar con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md) para obtener más información acerca de cómo realizar estas operaciones.  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>Generar un cliente de WCF o contrato de servicio WCF usando el Agregar referencia de servicio de adaptador complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para las operaciones de salida o código de servicio WCF para las operaciones de entrada.  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-sql-server-operations"></a>Para generar el contrato de servicio o clase de cliente WCF para las operaciones de SQL Server  
  
1.  En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar las operaciones de entrada o salidas.  
  
2.  Examinar o buscar categorías (por ejemplo, una tabla de base de datos) o de las operaciones específicas para el que desea generar un cliente WCF (o contrato de servicio WCF).   
    Por ejemplo, para buscar las operaciones en la tabla de empleados, en la **seleccione una categoría de** cuadro:  
  
    1.  Expanda el nodo raíz (**/**) para ver las categorías aparecen en la que las operaciones de una base de datos de SQL Server.  
  
    2.  En el nodo raíz, expanda la **tablas** nodo para ver las tablas disponibles.  
  
3.  Haga clic en el **empleado** nodo de la tabla y en el **categorías y operaciones disponibles** , seleccione las operaciones o categorías para el que desea generar un cliente WCF (o contrato de servicio WCF) y, a continuación, Haga clic en **agregar**. Las operaciones seleccionadas se muestran en la **agregar categorías y operaciones** cuadro.  
  
     La siguiente ilustración muestra la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] con la inserción y las operaciones Select para la tabla Employee seleccionado.  
  
     ![Generar el contrato de servicio o cliente WCF](../../adapters-and-accelerators/adapter-sql/media/sql-adap-add-adap-serv-ref.gif "sql_adap_add_adap_serv_ref")  
  
    > [!IMPORTANT]
    >  Dependiendo de las operaciones de salida (o categorías) que usted seleccione, más de un WCF puede generarse clase de cliente. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
4.  Para la mayoría de los escenarios, las opciones de serialización predeterminadas son suficientes; Sin embargo, si es necesario, puede controlar varios aspectos sobre el código que se genera y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
    1.  Haga clic en **opciones avanzadas** para abrir el **opciones avanzadas** cuadro.  
  
    2.  En el **opciones avanzadas** cuadro en **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si los métodos asincrónicos se generan para el cliente de WCF o deshabilitar la generación de un archivo de configuración.  
  
    3.  En **serializador** seleccionar el serializador que se debe usar.  
  
     La siguiente ilustración muestra la **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y no hay otras opciones están seleccionadas).  
  
     ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     Las opciones que puede configurar en el **opciones avanzadas** cuadro equivalen a algunas de las opciones disponibles cuando se usa la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx). 
  
5.  Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda la clase de cliente WCF (o la interfaz de servicio WCF) y código auxiliar para las operaciones y categorías que ha seleccionado en el directorio del proyecto. De forma predeterminada, también se guarda un archivo de configuración. Se generan archivos ligeramente diferentes para las operaciones de entrada y salidas; Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
 Puede seleccionar cualquier nodo que aparece en el **categorías y operaciones disponibles** cuadro. Si selecciona un nodo de categoría, a continuación, se seleccionarán todas las operaciones disponibles en ese nodo y sus nodos secundarios. Por ejemplo, para generar a un cliente WCF para todas las operaciones que aparecen para la tabla Employee, puede seleccionar el nodo de empleado.  
  
## <a name="see-also"></a>Vea también  
 [Obtiene los metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)