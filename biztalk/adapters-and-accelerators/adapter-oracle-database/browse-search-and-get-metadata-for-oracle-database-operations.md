---
title: Examinar, buscar y obtener los metadatos de las operaciones de base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF client, generating a
- operations, browsing for
- metadata, browsing
- browse, for operations
- schema, generating
- metadata, retrieving
- browse, metadata
- retrieve, metadata
- operations, searching for
- WCF service contract, generating a
- metadata, browsing, searching, and retrieving
ms.assetid: 65bd59e0-771d-40fe-966c-8cc8a629ce47
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7427ab96879c54b5a71435576da8a4610787dd6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="browse-search-and-get-metadata-for-oracle-database-operations"></a>Examinar, buscar y obtener los metadatos de las operaciones de base de datos de Oracle
Esta sección proporciona información sobre cómo usar [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Mediante el uso de estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes, puede:  
  
-   Buscar operaciones para el que se va a recuperar los metadatos.  
  
-   Buscar operaciones para el que se va a recuperar los metadatos.  
  
-   Agregar esquemas de mensaje para las operaciones seleccionadas y el puerto de los archivos de configuración de enlace a un proyecto de BizTalk server cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
-   Agregar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para operaciones seleccionadas y un archivo de configuración (app.config) a un proyecto de programación de BizTalk no cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
 Debe conectarse a la base de datos de Oracle para poder examinar, buscar o recuperar los metadatos para las operaciones de destino. Para obtener información acerca de cómo conectar con Oracle con la base de datos cuando se usa [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectar con base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md).  
  
> [!NOTE]
>  -   El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] presentes básicamente la misma interfaz al examinar y buscar las operaciones, por lo que los tres componentes se tratan en los temas de la mismos.  
> -   Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de esa categoría, por ejemplo, una tabla entera o esquema (o incluso todas las tablas en un esquema).  
  
## <a name="browsing-for-operations"></a>Búsqueda de operaciones  
 Al examinar los metadatos que utilizan [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies:  
  
-   Operaciones que se pueden realizar en las tablas, vistas, procedimientos almacenados, funciones y paquetes.  
  
-   La operación SQLEXECUTE, que permite a los clientes de adaptador ejecutar cualquier lenguaje de manipulación de datos genéricos (DML) o un procedimiento almacenado en una base de datos de Oracle.  
  
-   Las operaciones POLLINGSTMT y notificación, que permiten a los clientes de adaptador obtener datos de entrada de la base de datos de Oracle. También muestra una lista de procedimientos almacenados, funciones y paquetes en los respectivos esquemas que se exponen como operaciones de sondeo.  
  
> [!NOTE]
>  -   Mediante el uso de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], puede examinar los nodos de categoría y operación mediante una interfaz de Windows.  
> -   Se presentan las operaciones SQLEXECUTE, POLLINGSTMT y notificación directamente bajo el nodo raíz en el árbol de categorías. Debe seleccionar el nodo raíz para ver estas operaciones entrantes y salientes.  
  
 Para obtener más información acerca de los metadatos de exploración, consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
 Realice los pasos siguientes para buscar las operaciones expuestas para distintos artefactos en una base de datos de Oracle mediante la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
#### <a name="to-browse-metadata-in-an-oracle-database"></a>Para examinar los metadatos en una base de datos de Oracle  
  
1.  Conectarse a una base de datos de Oracle mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectar con base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3.  El **seleccione una categoría de** cuadro muestra los esquemas de la base de datos de Oracle. Haga clic en un esquema para ver las tablas, procedimientos, funciones, paquetes y vistas puede tener acceso al esquema en el **categorías y operaciones disponibles** cuadro. Como alternativa, puede ver la categorización, expanda el nodo de esquema.  
  
    > [!TIP]
    >  Puede ir directamente a la categoría "inmediata" nodos de subcategoría en el árbol, puede escribir el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccione una categoría de** cuadro. Por ejemplo, para saltar a la **SCOTT** nodo, mantener el foco en el nodo raíz y, a continuación, escriba `SCOTT`.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. El nodo de esquema SCOTT está seleccionado y los nodos de categoría general disponibles en el nodo de SCOTT se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar usuarios en una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/c6e02d12-278b-4419-8c8d-d12d0d64f325.gif "c6e02d12-278b-4419-8c8d-d12d0d64f325")  
  
4.  Haga clic en el **tabla** nodo para ver las tablas de SCOTT en la **categorías y operaciones disponibles** cuadro. Como alternativa, puede ver la lista de tablas expandiendo el **tabla** nodo.  
  
5.  Haga clic en un nombre de tabla para ver las operaciones admitidas en la tabla.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Las tablas disponibles en el esquema SCOTT se enumeran en la **seleccione una categoría de** cuadro. Las operaciones disponibles para la tabla EMP se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar tablas en una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d.gif "6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d")  
  
6.  Haga clic en el **procedimiento** nodo para mostrar los procedimientos que puede tener acceso al esquema SCOTT en la **categorías y operaciones disponibles** cuadro.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Los nodos de categoría general disponibles en el esquema SCOTT se enumeran en la **seleccione una categoría de** cuadro. Los procedimientos disponibles en el esquema SCOTT se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar procedimientos en una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/9826e160-5295-4fdc-bd82-ccd456d89242.gif "9826e160-5295-4fdc-bd82-ccd456d89242")  
  
7.  Haga clic en el **función** nodo para ver las funciones para el esquema SCOTT en la **categorías y operaciones disponibles** cuadro.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Los nodos de categoría general disponibles en el esquema SCOTT se enumeran en la **seleccione una categoría de** cuadro. Las funciones disponibles en el esquema SCOTT se muestran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar funciones en una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/ae02731e-7f26-4552-8e40-db797885af01.gif "ae02731e-7f26-4552-8e40-db797885af01")  
  
8.  Haga clic en el **paquete** nodo para ver los paquetes para el esquema SCOTT en la **categorías y operaciones disponibles** cuadro. Como alternativa, puede ver la lista de paquetes expandiendo el **paquete** nodo.  
  
9. Haga clic en un nombre de paquete para ver las operaciones admitidas en el paquete.  
  
     La siguiente ilustración muestra [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que muestra los paquetes y las operaciones admitidas para un paquete determinado, para el esquema SCOTT.  
  
     ![Examinar paquetes en una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/bts-r2-net-adapter-oracle-tut1-browse-pckgs.gif "bts_R2_NET_Adapter_Oracle_Tut1_Browse_Pckgs")  
  
10. Haga clic en el **vista** nodo para ver las vistas para el esquema SCOTT en la **categorías y operaciones disponibles** cuadro. Como alternativa, puede ver la lista de vistas expandiendo el **vista** nodo.  
  
11. Haga clic en el nombre de una vista para ver las operaciones admitidas en la vista.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que enumeran las vistas y las operaciones admitidas en una vista determinada, para el esquema SCOTT.  
  
     ![Examinar vistas en una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d.gif "cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d")  
  
    > [!NOTE]
    >  Con los modelos de canal y el servicio WCF, los clientes de adaptador pueden especificar un tamaño de lote para realizar una recuperación de lote de metadatos.  
  
## <a name="searching-for-operations"></a>Búsqueda de operaciones  
 Al buscar metadatos de Oracle mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   Admite caracteres comodín y escape en la expresión de búsqueda.  
  
-   Permite la búsqueda inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar una función, que debe ser buscando en \\\Functions [esquema]. No se admite la búsqueda de varios nivel.  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para buscar y su interpretación por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter<br /><br /> Por ejemplo, coincide con A_ AB, CA, AD.|  
|% (porcentaje)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un % coincide con A, AB ABC.|  
|\ (escape)|Convierte el significado especial de % y _<br /><br /> Por ejemplo, un\\_B coincide con A_B.|  
  
> [!NOTE]
>  Carácter de escape es un carácter que se coloca delante de un carácter comodín para indicar que el carácter comodín debe interpretarse como un carácter normal y no como un carácter comodín.  
  
 Para obtener más información consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
#### <a name="to-search-metadata-in-an-oracle-database"></a>Buscar metadatos en una base de datos de Oracle  
  
1.  Conectarse a una base de datos de Oracle mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectar con base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) para obtener instrucciones.  
  
2.  En el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si buscarán las operaciones de entrada o salidas mediante el adaptador de.  
  
3.  En el **seleccione una categoría de** cuadro, haga clic en el esquema que contiene tablas, procedimientos, funciones, paquetes y vistas que se va a buscar. Si no está seguro de qué esquema haga clic en, haga clic en el nodo raíz.  
  
4.  En el **búsqueda en la categoría** texto cuadro, escriba una expresión de búsqueda para buscar un esquema específico. Por ejemplo, para buscar los esquemas que contienen "SC" en su nombre, escriba **% SC** en el cuadro de texto.  
  
5.  Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. Una vez completada, la búsqueda del **categorías y operaciones disponibles** cuadro muestra los esquemas que cumplen los criterios de búsqueda.  
  
6.  En el **seleccione una categoría de** cuadro, expanda el nodo que corresponde al esquema y, a continuación, haga clic en la base de datos de elementos y que se va a buscar dentro de. En el **búsqueda en la categoría** texto cuadro, escriba una expresión de búsqueda para buscar un elemento específico de la base de datos.  
  
     Por ejemplo, para buscar las tablas que tienen "EMP" en sus nombres, seleccione **tabla**, tipo **% EMP** en el **búsqueda en la categoría** texto cuadro y, a continuación, haga clic en el botón con el icono de flecha derecha.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que muestra el resultado de búsqueda.  
  
     ![Buscar metadatos en una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/1ee912f8-896e-4b45-ba98-1bbd36b56574.gif "1ee912f8-896e-4b45-ba98-1bbd36b56574")  
  
    > [!NOTE]
    >  Con los modelos de canal y el servicio WCF, los clientes de adaptador pueden especificar un tamaño de lote para realizar una búsqueda batch-wise de metadatos.  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in-or-add-adapter-metadata-wizard"></a>Generar el esquema mediante la Consume Adapter Service complemento o metadatos Asistente para agregar adaptador  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para los artefactos seleccionados de base de datos de Oracle. Una vez examinar y buscar los artefactos que desea invocar, puede generar esquema para los artefactos y enviar mensajes, que se ajuste al esquema, base de datos Oracle. Realice los pasos siguientes para recuperar los metadatos de una base de datos de Oracle mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de esa categoría, por ejemplo, puede seleccionar una tabla completa (para generar esquemas para todas las operaciones en la tabla) o seleccione operaciones específicas en una tabla (por ejemplo, Insert y Delete) a Genere el esquema para solo esas operaciones en una tabla. Para obtener más información acerca de los nodos, consulte [IDs3 de nodo de metadatos](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>Para recuperar los metadatos de una base de datos de Oracle  
  
1.  Conectarse a una base de datos de Oracle mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Vea [conectar con base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3.  En el **seleccione una categoría** , expanda un nodo de esquema.  
  
4.  Seleccione la categoría para la que desea generar los metadatos. Por ejemplo, si desea generar metadatos de una tabla, seleccione **tabla**.  
  
5.  Expandir ese nodo de categoría determinada y seleccionar el elemento específico en ese nodo para el que desea generar los metadatos.  
  
     Por ejemplo, para generar metadatos para una tabla concreta, expanda la **tabla** nodo y seleccione el nombre de una tabla específica.  
  
    > [!NOTE]
    >  También puede buscar un elemento específico de la base de datos, como se describe en el procedimiento anterior.  
  
6.  En el **categorías y operaciones disponibles** cuadro, seleccione las operaciones que pertenecen al elemento de base de datos que seleccionó en el paso anterior y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas se muestran en la **agregar categorías y operaciones** cuadro.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que enumeran las operaciones seleccionadas.  
  
     ![Recuperar los metadatos de una base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/d3950566-8720-4c15-8a16-4ade14bf6221.gif "d3950566-8720-4c15-8a16-4ade14bf6221")  
  
     Si desea generar esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos complejo "CT1". Después de generar el esquema para "Op1" cerrar la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar el esquema para otra operación "Op2". Supongamos que "Op2" también contiene un parámetro de tipo de datos complejo "CT1". Después de salir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, se producirán errores de compilación porque el tipo de datos complejo "CT1" se define dos veces en distintos archivos XSD. En estas situaciones, se recomienda lo siguiente:  
  
    -   Generar esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejo "CT1".  
  
    -   Si desea generar esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar la **generar tipos de esquema únicos** casilla de verificación para que los archivos XSD generados contienen espacios de nombres únicos para los más complejos tipo de datos "CT1".  
  
7.  Haga clic en **Aceptar**. El archivo de esquema se guarda con una extensión .xsd en la misma ubicación que el proyecto de BizTalk.  
  
     De forma predeterminada, los archivos se crean con la convención de nomenclatura "OracleDBBindingSchema\<n\>.xsd", donde ' n ' puede ser 1, 2 y así sucesivamente, dependiendo del número de archivos de esquema creados. Como alternativa, puede proporcionar un nombre personalizado para los archivos de esquema, escriba un nombre en el **prefijo de nombre de archivo** cuadro de texto. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] ahora crea archivos de esquema con la convención de nomenclatura \<el prefijo del nombre de archivo\>esquema\<n\>.xsd.  
  
    > [!NOTE]
    >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace especificado al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la consola de administración de BizTalk Server para crear un puerto de WCF-Custom con el URI, propiedades de enlace de conexión y establece la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
    > [!IMPORTANT]
    >  Mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] no genera un archivo de enlace.  
  
8.  En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>Generar un cliente de WCF o contrato de servicio WCF usando el Agregar referencia de servicio de adaptador complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para las operaciones de salida o código de servicio WCF para las operaciones de entrada.  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>Para recuperar los metadatos de una base de datos de Oracle  
  
1.  En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si se va a realizar operaciones de salida o entrante (POLLINGSTMT).  
  
2.  Examinar o buscar categorías (por ejemplo, una tabla de base de datos de Oracle) o de las operaciones específicas para el que desea generar un cliente WCF (o contrato de servicio WCF).   
    Por ejemplo, para buscar las operaciones en el SCOTT. Tabla EMP en la **seleccione una categoría de** cuadro:  
  
    1.  Expanda el nodo raíz (**/**) para ver los esquemas que aparecen para la base de datos de Oracle.  
  
    2.  En el nodo raíz, expanda la **SCOTT** nodo para ver las categorías que se exponen para el esquema SCOTT.  
  
    3.  En el **SCOTT** nodo, expanda el **tabla** exhibe de nodo para ver las tablas para el esquema SCOTT.  
  
    4.  En el **tabla** seleccione nodo el **EMP** nodo. Las operaciones que exhibe para la tabla EMP se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
3.  En el **categorías y operaciones disponibles** , seleccione las operaciones o categorías que desea generar un cliente de WCF (o un contrato de servicio WCF) y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas se muestran en la **agregar categorías y operaciones** cuadro.  
  
     La siguiente ilustración muestra la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] con las operaciones Insert y Update para la SCOTT. Tabla EMP seleccionada.  
  
     ![Se seleccionan las operaciones Select y Update. ] (../../adapters-and-accelerators/adapter-oracle-database/media/4c41ac7b-784a-494c-ac82-c007e22a4fdf.gif "4c41ac7b-784a-494c-ac82-c007e22a4fdf")  
  
    > [!IMPORTANT]
    >  Dependiendo de las operaciones de salida (o categorías) que usted seleccione, más de un WCF puede generarse clase de cliente. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
4.  Para la mayoría de los escenarios, las opciones de serialización predeterminadas son suficientes; Sin embargo, si es necesario, puede controlar varios aspectos sobre el código que se genera y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
    1.  Haga clic en **opciones avanzadas** para abrir el **opciones avanzadas** cuadro.  
  
    2.  En el **opciones avanzadas** cuadro en **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si los métodos asincrónicos se generan para el cliente de WCF o deshabilitar la generación de un archivo de configuración.  
  
    3.  En **serializador** seleccionar el serializador que se debe usar.  
  
     La siguiente ilustración muestra la **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y no hay otras opciones están seleccionadas).  
  
     ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     Las opciones que puede configurar en el **opciones avanzadas** cuadro equivalen a algunas de las opciones disponibles cuando se usa la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
5.  Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda la clase de cliente WCF (o la interfaz de servicio WCF) y código auxiliar para las operaciones y categorías que ha seleccionado en el directorio del proyecto. De forma predeterminada, también se guarda un archivo de configuración. Se generan archivos ligeramente diferentes para las operaciones de entrada y salidas; Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
 Puede seleccionar cualquier nodo que aparece en el **categorías y operaciones disponibles** cuadro. Si selecciona un nodo de categoría, a continuación, se seleccionarán todas las operaciones disponibles en ese nodo y sus nodos secundarios. Por ejemplo, para generar a un cliente WCF para todas las operaciones que exhibe para la tabla EMP, puede seleccionar el nodo EMP; para generar a clientes WCF para todas las tablas en el esquema SCOTT, puede seleccionar el nodo de la tabla; y así sucesivamente.  
  
## <a name="see-also"></a>Vea también  
[Obtener los metadatos de las operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)