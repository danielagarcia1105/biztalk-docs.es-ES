---
title: Examinar, buscar y obtener metadatos para operaciones de RFC de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- browsing, RFCs
- RFCs, searching
- RFCs, browsing
- RFC operations, generating schema
- RFC operations
- searching, RFCs
- WCF client, generating a
ms.assetid: 68d9e7b2-b8ab-47f5-afda-2811f68e834b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c712075358cfacfbbf2ae3478f76fd64b78db6ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966949"
---
# <a name="browse-search-and-get-metadata-for-rfc-operations-in-sap"></a>Examinar, buscar y obtener metadatos para operaciones de RFC de SAP
Esta sección proporciona instrucciones sobre cómo examinar, buscar y recuperar metadatos de SAP para las operaciones de RFC mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. La mayoría de las instrucciones es los misma para toda la interfaz de usuario de tres. Siempre que se proporcionan procedimientos de procede, independientes de la interfaz de usuario correspondientes.  
  
 Antes de realizar los pasos proporcionados en las secciones siguientes, debe tener:  
  
- Crea un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto.  
  
- Conectado al sistema SAP con [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener instrucciones, consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).  
  
## <a name="browsing-rfcs-in-an-sap-system"></a>Examinar los RFC en un sistema SAP  
 Al examinar los metadatos mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies:  
  
- Solicitudes de cambio como operaciones que se pueden invocar en el sistema SAP.  
  
- Operación RfcGetAttributes, lo que permite a los clientes del adaptador obtener información sobre los parámetros de conexión RFC.  
  
  Para obtener más información acerca de la exploración de metadatos de SAP, consulte [exponer la configuración de adaptador como una propiedad de enlace mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md).
  
  Realice los pasos siguientes para examinar los RFC en un sistema SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-browse-rfcs-in-an-sap-system"></a>Para examinar los RFC en un sistema SAP  
  
1. Conectarse a un servidor de SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el nodo RFC para ver los grupos funcionales RFC en la **operaciones y categorías disponibles** cuadro. Como alternativa, también puede ver los grupos funcionales RFC, expanda el nodo RFC.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **base** grupo funcional RFC, mantener el foco en el **RFC** nodo y, a continuación, escriba `Basis`.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar los grupos funcionales RFC.  
  
    ![Examinar grupos funcionales de RFC](../../adapters-and-accelerators/adapter-sap/media/958cba26-1644-4700-a647-9eeb0273ebd1.gif "958cba26-1644-4700-a647-9eeb0273ebd1")  
  
4. Haga clic en los grupos funcionales RFC para ver las RFC relevantes. La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] con los documentos RFC en un determinado grupo funcional RFC.  
  
    ![Examinar los RFC en un grupo funcional](../../adapters-and-accelerators/adapter-sap/media/bf725aa9-a547-4f20-8246-d9c8fedadb40.gif "bf725aa9-a547-4f20-8246-d9c8fedadb40")  
  
## <a name="searching-rfcs-in-an-sap-system"></a>Buscar RFC en un sistema SAP  
 Al buscar los metadatos para RFC en un sistema SAP mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- Admite caracteres comodín en la expresión de búsqueda.  
  
- Permite la búsqueda se encuentra inmediatamente debajo del nodo en el que se realiza la operación de búsqueda.  
  
  La tabla siguiente enumeran los caracteres especiales que se pueden usar para la búsqueda y su interpretación por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|+ (más)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, A + coincide con AB, CA, AD|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * coincide con A, AB ABC.|  
  
 Para obtener más información acerca de los caracteres especiales admitidas por el adaptador, vea [exponer la configuración de adaptador como una propiedad de enlace mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md).
  
 Realice los pasos siguientes para buscar RFC en un sistema SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-search-rfcs-in-an-sap-system"></a>Para buscar RFC en un sistema SAP  
  
1. Conectarse a un servidor de SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si buscarán las operaciones entrantes o salientes mediante el adaptador.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el grupo funcional RFC que contiene la solicitud de cambio que desea buscar. Si no está seguro de qué grupo funcional para buscar en, haga clic en el nodo RFC de raíz.  
  
4. En el **búsqueda en la categoría** texto, escriba una expresión de búsqueda para buscar una RFC específica. Por ejemplo, para buscar las solicitudes de cambio que tienen "RFC_CUST" en sus nombres, escriba * RFC_CUST\* en el cuadro de texto.  
  
5. Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. Una vez completada la búsqueda, el **operaciones y categorías disponibles** cuadro enumeran los documentos RFC que cumplen los criterios de búsqueda.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar la RFC de resultado de búsqueda.  
  
    ![Buscar RFC en un sistema SAP](../../adapters-and-accelerators/adapter-sap/media/2cf0b262-bbc7-4d0f-a9cf-5b090fb744b6.gif "2cf0b262-bbc7-4d0f-a9cf-5b090fb744b6")  
  
## <a name="generating-schema-for-biztalk-projects"></a>Generar el esquema para los proyectos de BizTalk  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para los artefactos SAP seleccionados. Después de examinar y buscar los artefactos que desea invocar, puede generar el esquema para aquellos artefactos y enviar mensajes, que se ajuste al esquema, al sistema SAP.  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de la categoría, por ejemplo, puede seleccionar un grupo funcional RFC completo (para generar el esquema para todos los documentos RFC en ese grupo) o seleccione RFC específicas para generar el esquema para solo esas RFC. Para obtener más información acerca de los nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
#### <a name="to-retrieve-metadata-for-rfcs"></a>Para recuperar metadatos para RFC  
  
1. Conectarse a un servidor de SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el grupo funcional RFC que contiene la solicitud de cambio para el que desea generar los metadatos.  
  
    También puede buscar las solicitudes de cambio específicos. Por ejemplo, para buscar las solicitudes de cambio que contienen "RFC_CUST" en su nombre, haga clic en el nodo RFC and en la **búsqueda en la categoría** cuadro de texto escriba \*RFC_CUST\*. Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. El **operaciones y categorías disponibles** cuadro enumera todos los documentos RFC que tienen "RFC_CUST" en su nombre.  
  
4. En el **operaciones y categorías disponibles** , seleccione las RFC para los que desea generar los metadatos y haga clic en **agregar**. Las RFC seleccionadas aparecen en la **agregar categorías y operaciones** cuadro.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar las RFC seleccionadas.  
  
    ![Recuperar metadatos para RFC](../../adapters-and-accelerators/adapter-sap/media/f7c89882-e2d7-409b-af2e-e35c7268c137.gif "f7c89882-e2d7-409b-af2e-e35c7268c137")  
  
    Si desea generar el esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos complejos "CT1". Después de generar el esquema para "Op1" cerrar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar esquemas para otra operación "Op2". Suponga que "Op2" también contiene un parámetro de tipo de datos complejos "CT1". Después de salir el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, recibirá errores de compilación porque se define el tipo de datos complejos "CT1" dos veces en distintos archivos XSD. En tales situaciones, se recomienda lo siguiente:  
  
   - Genere el esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejos "CT1".  
  
   - Si desea generar el esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar el **generar tipos de esquema únicos** casilla de verificación para que los archivos XSD generados contienen espacios de nombres únicos para el complejo tipo de datos "CT1".  
  
5. Haga clic en **Aceptar**. El archivo de esquema se guarda con la extensión .xsd en la misma ubicación que el proyecto de BizTalk.  
  
   > [!NOTE]
   >  Si usas [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], de forma predeterminada, los archivos se crean con la convención de nomenclatura "SAPBinding\<n > .xsd", donde "n" puede ser 1, 2, etc. según el número de archivos de esquema creado. Como alternativa, puede proporcionar un nombre personalizado para los archivos de esquema escribiendo un nombre en el **prefijo de nombre de archivo** cuadro de texto. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] ahora crea archivos de esquema con la convención de nomenclatura \<prefijo de nombre de archivo >\<n > XSD.  
   > 
   > [!NOTE]
   >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace que especificó al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la consola de administración de BizTalk Server para crear un puerto de WCF-Custom con la conexión URI, propiedades de enlace, y establezca la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
6. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="generating-a-wcf-client-for-rfc-operations-using-the-add-adapter-service-reference-plug-in"></a>Generación de un cliente WCF para las operaciones de RFC mediante el Add Adapter Service Reference complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para enviar documentos RFC a SAP system o WCF service contrato y el código para recibir las solicitudes de cambio (servidor RFC) desde el sistema SAP.  
  
#### <a name="to-generate-a-wcf-client-or-a-wcf-service-contract-for-rfcs"></a>Para generar un cliente de WCF o un contrato de servicio WCF para las solicitudes de cambio  
  
1. En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones de salida o entrante (servidor RFC).  
  
2. En el **seleccionar una categoría** , expanda el **RFC** nodo y, a continuación, haga clic en el grupo funcional RFC que contiene la solicitud de cambio para el que desea generar un cliente de WCF o un contrato de servicio WCF.  
  
    También puede buscar las solicitudes de cambio. Por ejemplo, para buscar las solicitudes de cambio que contienen "RFC_CUST" en su nombre, haga clic en el **RFC** nodo y, en el **búsqueda en la categoría** cuadro de texto escriba \*RFC_CUST\*. Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. El **operaciones y categorías disponibles** cuadro enumera todos los documentos RFC que tienen "RFC_CUST" en su nombre.  
  
3. En el **operaciones y categorías disponibles** , seleccione las operaciones o categorías (grupos funcionales RFC) para el que desea generar un cliente de WCF (o un contrato de servicio WCF) y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas aparecen en la **agregar categorías y operaciones** cuadro. Puede seleccionar cualquier nodo que aparece en el **operaciones y categorías disponibles** cuadro. Si selecciona un nodo de categoría, se agregará todas las operaciones disponibles en ese nodo y sus nodos secundarios.  
  
4. Para la mayoría de los escenarios son suficientes; las opciones de serialización predeterminado Sin embargo, si es necesario, puede controlar varios aspectos sobre el código generado y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
   1. Haga clic en **opciones avanzadas** para abrir el **opciones avanzadas** cuadro.  
  
   2. En el **opciones avanzadas** cuadro bajo **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si los métodos asincrónicos se generan para el cliente de WCF o deshabilitar la generación de un archivo de configuración.  
  
   3. En **serializador** selecciona el serializador que se debe usar.  
  
      La siguiente ilustración muestra el **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y ninguna otra opción que se ha seleccionado).  
  
      ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      Las opciones que se pueden configurar en el **opciones avanzadas** cuadro son equivalentes a algunas de las opciones disponibles al utilizar ServiceModel Metadata Utility Tool (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
5. Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda la clase de cliente WCF (o la interfaz de servicio WCF) y código auxiliar para las operaciones y categorías que ha seleccionado en el directorio del proyecto. De forma predeterminada, también se guarda un archivo de configuración. Se generan archivos ligeramente diferentes para las operaciones de entrada y salidas; Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)