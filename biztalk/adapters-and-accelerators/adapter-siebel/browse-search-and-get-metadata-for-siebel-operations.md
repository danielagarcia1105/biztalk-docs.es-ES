---
title: Examinar, buscar y obtener metadatos para operaciones de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving
- how to, browse metadata
- how to, retrieve metadata
- retrieving, metadata
- metadata, browsing
- browsing, metadata
- metadata, searching
- how to, seach metadata
- searching, metadata
ms.assetid: 7e474d8e-b030-47ea-b1b6-8048cddbba8a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4f6821f252bf2854b7ed64f57cbdf742c378c5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991421"
---
# <a name="browse-search-and-get-metadata-for-siebel-operations"></a>Examinar, buscar y obtener metadatos para operaciones de Siebel
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Si se utilizan [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes, puede:  
  
- Buscar operaciones para que se va a recuperar los metadatos.  
  
- Búsqueda de operaciones que se va a recuperar los metadatos.  
  
- Agregar esquemas de mensaje para operaciones seleccionadas y el puerto de los archivos de configuración de enlace a un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
- Agregar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para las operaciones seleccionadas y un archivo de configuración (app.config) a un proyecto de programación que no sean de BizTalk cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes esencialmente la misma interfaz al examinar y buscar las operaciones, por lo que los tres componentes se tratan en los mismos temas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a un sistema Siebel antes de que puede examinar, buscar o recuperar metadatos para operaciones de destino. Para obtener información acerca de cómo conectarse a un sistema Siebel cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectar con el sistema Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md).  
  
## <a name="browsing-metadata"></a>Examinar los metadatos  
 Al examinar los metadatos mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies:  
  
-   Las operaciones que se pueden realizar en componentes empresariales de Siebel, como insertarán, consultar, actualizarán y eliminarán.  
  
-   Métodos de servicio empresarial que se pueden invocar los clientes del adaptador.  
  
> [!NOTE]
>  Mediante el uso de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], puede examinar la categoría y el funcionamiento de los nodos mediante una interfaz de Windows.  
  
 Para obtener más información acerca de la exploración de metadatos de Siebel, consulte [examinar, buscar y obtener metadatos de Siebel](../../adapters-and-accelerators/adapter-siebel/browse-search-and-get-siebel-metadata.md) 
  
 Realice los pasos siguientes para examinar los metadatos de un sistema de Siebel mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-browse-metadata-in-a-siebel-system"></a>Para examinar los metadatos en un sistema de Siebel  
  
1. Conectarse a un sistema de Siebel mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con el sistema Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3. El **seleccionar una categoría** cuadro listas el **objetos de negocios** y **servicios empresariales** nodos. Haga clic en el **objetos de negocios** nodo para ver una lista de objetos comerciales en el **operaciones y categorías disponibles** cuadro. Como alternativa, puede ver la lista de objetos de negocios expandiendo el **objetos de negocios** nodo.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **cuenta** objeto comercial, mantener el foco en el **objetos de negocios** nodo y, a continuación, escriba `Account`.  
  
4. Haga clic en los objetos de negocio para ver la lista de componentes de negocios para un objeto de negocios determinado. Como alternativa, puede ver la lista de componentes empresariales mediante la expansión de un objeto de negocios.  
  
5. Haga clic en los componentes empresariales para ver la lista de operaciones admitidas para el componente empresarial determinado.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que muestra el objeto de negocios, los componentes empresariales y las operaciones admitidas.  
  
    ![Examinar componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/media/11c63383-4269-4ba0-909b-e2cbec7eae04.gif "11c63383-4269-4ba0-909b-e2cbec7eae04")  
  
6. Haga clic en el **servicios empresariales** nodo para ver una lista de servicios empresariales en la **operaciones y categorías disponibles** cuadro. Como alternativa, puede ver la lista de tablas expandiendo el **servicios empresariales** nodo.  
  
7. Haga clic en los servicios de negocios para ver la lista de métodos de servicio empresarial correspondiente.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que enumera los servicios de negocios y los métodos de servicio empresarial correspondiente.  
  
    ![Examinar servicios empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/media/60405c18-6035-42a5-851f-a0ed6d0570d6.gif "60405c18-6035-42a5-851f-a0ed6d0570d6")  
  
## <a name="searching-metadata"></a>Buscar metadatos  
 Al buscar metadatos de Siebel mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]:  
  
- Admite caracteres comodín y escape.  
  
- Permite la búsqueda se encuentra inmediatamente debajo del nodo en el que se realiza la operación de búsqueda. Por ejemplo, para buscar un servicio empresarial, debe buscar en servicios \Business.  
  
  La tabla siguiente enumeran los caracteres especiales que se pueden usar para la búsqueda y su interpretación por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|? (signo de interrogación)|Coincide exactamente con un carácter<br /><br /> ¿Por ejemplo, un? coincide con AB, CA, AD.|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * coincide con A, AB ABC.|  
  
 Realice los pasos siguientes para buscar metadatos en un sistema de Siebel mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-search-metadata-in-a-siebel-system"></a>Buscar metadatos en un sistema de Siebel  
  
1. Conectarse a un sistema de Siebel mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con el sistema Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el **Client (Outbound operations)** contrato.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el **objeto comercial** nodo.  
  
4. Para buscar un objeto de negocios determinado, haga clic en el **objetos de negocios** nodo en el **búsqueda en la categoría** texto y escriba una expresión de búsqueda. Por ejemplo, para buscar objetos de negocios que tienen nombres que empiezan con "Cuenta", escriba **cuenta\\*** en el cuadro de texto.  
  
5. Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. Una vez completada la búsqueda, el **operaciones y categorías disponibles** cuadro muestra los objetos de negocio que cumplen los criterios de búsqueda.  
  
6. Para buscar por un componente empresarial determinado en un objeto de negocios, haga clic en un objeto de negocios y en el **búsqueda en la categoría** cuadro de texto escriba una expresión de búsqueda. Por ejemplo, para buscar componentes empresariales que tienen nombres que empiezan con "Cuenta", escriba **cuenta\\*** en el cuadro de texto.  
  
7. Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. Una vez completada la búsqueda, el **operaciones y categorías disponibles** cuadro muestra los componentes empresariales que satisfacen los criterios de búsqueda.  
  
8. Para buscar operaciones determinadas para un componente empresarial, haga clic en un componente empresarial y en el **búsqueda en la categoría** cuadro de texto escriba una expresión de búsqueda. Por ejemplo, para buscar las operaciones que tengan nombres que comienzan con "Query", escriba **consulta\\*** en el cuadro de texto.  
  
9. Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. Una vez completada la búsqueda, el **operaciones y categorías disponibles** cuadro muestra los componentes empresariales que satisfacen los criterios de búsqueda.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que muestra el resultado de búsqueda.  
  
     ![Buscar componentes empresariales](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-04-search.gif "SIEBEL-ADPT-Lesson1-Step3-04-search")  
  
     Llevar a cabo un procedimiento similar para buscar en el **servicio empresarial** nodo.  
  
## <a name="generating-schema-for-biztalk-projects"></a>Generar el esquema para los proyectos de BizTalk  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para los artefactos seleccionados de Siebel. Después de examinar y buscar los artefactos que desea invocar, puede generar el esquema para aquellos artefactos y enviar mensajes, que se ajuste al esquema, para Siebel.  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de la categoría, por ejemplo, puede seleccionar un componente empresarial (para generar el esquema para todas las operaciones del componente empresarial) o seleccione operaciones específicas en un componente empresarial (para ejemplo, Insert y Delete) para generar el esquema solo esas operaciones. Para obtener más información acerca de los nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).  
  
#### <a name="to-generate-schema-for-siebel-artifacts"></a>Para generar el esquema para los artefactos de Siebel  
  
1. Conectarse a un sistema de Siebel mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Consulte [conectar con el sistema Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el **Client (Outbound operations)** contrato.  
  
3. En el **seleccionar una categoría** cuadro, expanda el nodo de servicio de negocio o un objeto de negocios.  
  
4. En el **operaciones y categorías disponibles** , seleccione los componentes empresariales o servicios de negocio o las operaciones correspondientes para el que desea generar los metadatos y, a continuación, haga clic en **agregar**. Las operaciones o las áreas funcionales seleccionadas aparecen en la **agregar categorías y operaciones** cuadro.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], que enumera las operaciones seleccionadas.  
  
    ![Recuperar metadatos para objeto empresarial](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-05-get.gif "SIEBEL-ADPT-Lesson1-Step3-05-get")  
  
    Si desea generar el esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos complejos "CT1". Después de generar el esquema para "Op1" cerrar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar esquemas para otra operación "Op2". Suponga que "Op2" también contiene un parámetro de tipo de datos complejos "CT1". Después de salir el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, recibirá errores de compilación porque se define el tipo de datos complejos "CT1" dos veces en distintos archivos XSD. En tales situaciones, se recomienda lo siguiente:  
  
   - Genere el esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejos "CT1".  
  
   - Si desea generar el esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar el **generar tipos de esquema únicos** casilla de verificación para que los archivos XSD generados contienen espacios de nombres únicos para el complejo tipo de datos "CT1".  
  
5. Haga clic en **Aceptar**. El archivo de esquema se guarda con la extensión .xsd en la misma ubicación que el proyecto de BizTalk.  
  
    De forma predeterminada, los archivos se crean con la convención de nomenclatura "SiebelBindingSchema\<n\>.xsd", donde "n" puede ser 1, 2 y así sucesivamente, dependiendo del número de archivos de esquema creado. Como alternativa, puede proporcionar un nombre personalizado para los archivos de esquema escribiendo un nombre en el **prefijo de nombre de archivo** cuadro de texto. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] ahora crea archivos de esquema con la convención de nomenclatura \<prefijo de nombre de archivo\>esquema\<n\>.xsd.  
  
   > [!NOTE]
   >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace que especificó al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la consola de administración de BizTalk Server para crear un puerto de WCF-Custom con la conexión URI, propiedades de enlace, y establezca la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).  
  
6. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="generating-a-wcf-client-using-the-add-adapter-service-reference-plug-in"></a>Generar un cliente WCF mediante el Add Adapter Service Reference complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para las operaciones de salida en un sistema Siebel.  
  
#### <a name="to-generate-a-wcf-client"></a>Para generar a un cliente de WCF  
  
1. En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione **Client (Outbound operations)**.  
  
2. En el **seleccionar una categoría** cuadro, expanda el nodo de servicio de negocio o un objeto de negocios.  
  
3. En el **operaciones y categorías disponibles** , seleccione los componentes empresariales, servicios de negocio o las operaciones correspondientes para el que desea generar un cliente de WCF y, a continuación, haga clic en **agregar**. Las operaciones o las áreas funcionales seleccionadas aparecen en la **agregar categorías y operaciones** cuadro. Puede seleccionar cualquier nodo que aparece en el **operaciones y categorías disponibles** cuadro. Si selecciona un nodo de categoría, se seleccionarán todas las operaciones disponibles en ese nodo y sus nodos secundarios.  
  
   > [!IMPORTANT]
   >  Dependiendo de las categorías y las operaciones que seleccione, se puede generar más de una clase de cliente WCF. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).  
  
4. Para la mayoría de los escenarios son suficientes; las opciones de serialización predeterminado Sin embargo, si es necesario, puede controlar varios aspectos sobre el código generado y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
   1. Para abrir el **opciones avanzadas** cuadro, haga clic en **opciones avanzadas**.  
  
   2. En el **opciones avanzadas** cuadro bajo **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si se generan los métodos asincrónicos para el cliente de WCF, o puede deshabilitar la generación de un archivo de configuración.  
  
   3. En **serializador**, seleccione el serializador que se debe usar.  
  
      La siguiente ilustración muestra el **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y ninguna otra opción que se ha seleccionado).  
  
      ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      Las opciones que se pueden configurar en el **opciones avanzadas** cuadro son equivalentes a algunas de las opciones disponibles al utilizar ServiceModel Metadata Utility Tool (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
5. Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda el cliente de WCF de clase y código auxiliar para las operaciones y categorías que ha seleccionado en el directorio del proyecto. De forma predeterminada, también se guarda un archivo de configuración. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)