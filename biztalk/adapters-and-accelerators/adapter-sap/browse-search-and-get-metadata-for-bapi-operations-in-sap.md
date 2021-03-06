---
title: Examinar, buscar y obtener metadatos para operaciones de BAPI de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations
- WCF client, generating for BAPI operations
- BAPIs, browsing
- searching, BAPIs
- browsing, BAPIs
- BAPIs, searching
- BAPI operations, generating schema
ms.assetid: 2884215a-ddba-40c7-bf9f-bfc7831f90bb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97a043c08cf8d7ef258ceb2a2f311d2a86302881
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978957"
---
# <a name="browse-search-and-get-metadata-for-bapi-operations-in-sap"></a>Examinar, buscar y obtener metadatos para operaciones de BAPI de SAP
Esta sección proporciona instrucciones sobre cómo examinar, buscar y recuperar metadatos de SAP para las operaciones de BAPI mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. La mayoría de las instrucciones es los misma para toda la interfaz de usuario de tres. Siempre que se proporcionan procedimientos de procede, independientes de la interfaz de usuario correspondientes.  
  
 Antes de realizar los pasos proporcionados en las secciones siguientes, debe tener:  
  
- Crea un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto.  
  
- Conectado al sistema SAP con [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener instrucciones, consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).  
  
## <a name="browsing-bapis-in-an-sap-system"></a>Exploración BAPI en un sistema SAP  
 Al examinar los metadatos mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies BAPI como objetos de negocios, como las solicitudes de cambio. Exploración BAPI como RFC es similar a una solicitud de cambio de exploración en un sistema SAP. En tal caso, están disponibles como las solicitudes de cambio en las BAPI el **RFC**. Para obtener más información sobre las solicitudes de cambio de exploración, consulte [examinar, buscar y obtener metadatos para operaciones de RFC de SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md).  
  
 En esta sección se proporciona información sobre exploración BAPI como objetos de negocios. Para obtener más información acerca de la exploración de metadatos de SAP, consulte [¿cómo los metadatos de SAP de superficie de adaptador?](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 Realice los pasos siguientes para buscar BAPI en un sistema SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
 
  
#### <a name="to-browse-bapis-in-an-sap-system"></a>Para buscar BAPI en un sistema SAP  
  
1. Conectarse a un servidor de SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el nodo BAPI para ver las áreas funcionales de BAPI en el **operaciones y categorías disponibles** cuadro. Como alternativa, también puede ver las áreas funcionales BAPI, expanda el nodo BAPI.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **control** área funcional de BAPI, mantener el foco en el **BAPI** nodo y, a continuación, escriba `Controlling`.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar las áreas funcionales BAPI.  
  
    ![Examinar áreas funcionales en una BAPI](../../adapters-and-accelerators/adapter-sap/media/d4b03725-44d2-449d-a035-491cd7415139.gif "d4b03725-44d2-449d-a035-491cd7415139")  
  
4. Haga clic en el área funcional de BAPI para ver las categorizaciones de más de área funcional de BAPI.  
  
5. Haga clic en el área funcional de BAPI para ver las operaciones pertinentes admitidas para esa área funcional. La siguiente ilustración muestra la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] con las operaciones admitidas para un área funcional determinada.  
  
    ![Examinar operaciones para una BAPI](../../adapters-and-accelerators/adapter-sap/media/1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea.gif "1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea")  
  
## <a name="searching-bapis-in-an-sap-system"></a>Buscar BAPI en un sistema SAP  
 Al buscar metadatos en un sistema SAP mediante BAPI [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- Admite caracteres comodín en la expresión de búsqueda.  
  
- Permite la búsqueda se encuentra inmediatamente debajo del nodo en el que se realiza la operación de búsqueda.  
  
  La tabla siguiente enumeran los caracteres especiales que se pueden usar para la búsqueda y su interpretación por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|+ (más)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, A + coincide con AB, CA, AD|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * coincide con A, AB ABC.|  
  
 Para obtener más información acerca de los caracteres especiales admitidas por el adaptador, vea [¿cómo los metadatos de SAP de superficie de adaptador?](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 Realice los pasos siguientes para buscar BAPI en un sistema SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-search-bapis-in-an-sap-system"></a>Para buscar BAPI en un sistema SAP  
  
1. Conectarse a un servidor de SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si buscarán las operaciones entrantes o salientes mediante el adaptador.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el área funcional BAPI que contiene el BAPI que desea buscar.  
  
   > [!NOTE]
   >  Puede buscar BAPI solo en el nivel raíz.  
  
4. En el **búsqueda en la categoría** texto, escriba una expresión de búsqueda para buscar una BAPI específica. Por ejemplo, para buscar BAPI que tienen "Cuenta" en sus nombres, escriba * cuenta\* en el cuadro de texto.  
  
5. Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. Una vez completada la búsqueda, el **operaciones y categorías disponibles** cuadro enumeran las BAPI que cumplen los criterios de búsqueda.  
  
6. La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar la BAPI de resultado de búsqueda.  
  
    ![Buscar BAPI en un sistema SAP](../../adapters-and-accelerators/adapter-sap/media/82771a47-b656-473e-a96d-998bced38b35.gif "82771a47-b656-473e-a96d-998bced38b35")  
  
## <a name="generating-schema-for-biztalk-projects"></a>Generar el esquema para los proyectos de BizTalk  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para los artefactos SAP seleccionados. Después de examinar y buscar los artefactos que desea invocar, puede generar el esquema para aquellos artefactos y enviar mensajes, que se ajuste al esquema, al sistema SAP.  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de la categoría, por ejemplo, puede seleccionar toda una BAPI Sub funcional son (generar el esquema para todas las BAPI de ese grupo) o seleccione BAPI específico para generar el esquema para solo esos BAPI. Para obtener más información acerca de los nodos, consulte [metadatos nodo IDs4](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
#### <a name="to-retrieve-metadata-for-bapis"></a>Para recuperar los metadatos de BAPI  
  
1. Conectarse a un servidor de SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3. En el **seleccionar una categoría** cuadro, haga clic en el grupo funcional BAPI que contiene el BAPI para el que desea generar los metadatos.  
  
4. En el **operaciones y categorías disponibles** , seleccione las áreas funcionales u operaciones para el que desea generar los metadatos y haga clic en **agregar**. Las operaciones o las áreas funcionales seleccionadas aparecen en la **agregar categorías y operaciones** cuadro.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar las BAPI seleccionadas.  
  
    ![Recuperar metadatos para una BAPI](../../adapters-and-accelerators/adapter-sap/media/74170978-aef0-46c9-a6e2-36d6e9c2aefc.gif "74170978-aef0-46c9-a6e2-36d6e9c2aefc")  
  
    Si desea generar el esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos complejos "CT1". Después de generar el esquema para "Op1" cerrar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar esquemas para otra operación "Op2". Suponga que "Op2" también contiene un parámetro de tipo de datos complejos "CT1". Después de salir el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, recibirá errores de compilación porque se define el tipo de datos complejos "CT1" dos veces en distintos archivos XSD. En tales situaciones, se recomienda lo siguiente:  
  
   - Genere el esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejos "CT1".  
  
   - Si desea generar el esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar el **generar tipos de esquema únicos** casilla de verificación para que los archivos XSD generados contienen espacios de nombres únicos para el complejo tipo de datos "CT1".  
  
5. Haga clic en **Aceptar**. El archivo de esquema se guarda con la extensión .xsd en la misma ubicación que el proyecto de BizTalk.  
  
   > [!NOTE]
   >  Si usas [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], de forma predeterminada, los archivos se crean con la convención de nomenclatura "SAPBinding\<n\>.xsd", donde "n" puede ser 1, 2, etc. según el número de archivos de esquema creado. Como alternativa, puede proporcionar un nombre personalizado para los archivos de esquema escribiendo un nombre en el **prefijo de nombre de archivo** cuadro de texto. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] ahora crea archivos de esquema con la convención de nomenclatura \<prefijo de nombre de archivo\>\<n\>.xsd.  
   > 
   > [!NOTE]
   >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace que especificó al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la consola de administración de BizTalk Server para crear un puerto de WCF-Custom con la conexión URI, propiedades de enlace, y establezca la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
6. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="generating-a-wcf-client-for-bapi-operations-using-the-add-adapter-service-reference-plug-in"></a>Generación de un cliente WCF para las operaciones de BAPI mediante el Add Adapter Service Reference complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para las operaciones de BAPI (no se admiten operaciones de entrada para BAPI).  
  
#### <a name="to-generate-a-wcf-client-for-bapis"></a>Para generar a un cliente WCF para BAPI  
  
1. En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione **Client (Outbound operations)**.  
  
2. En el **seleccionar una categoría** , expanda el **BAPI** nodo y, a continuación, examinar o buscar las categorías BAPI o las operaciones para el que desea generar un cliente de WCF.  
  
3. En el **operaciones y categorías disponibles** , seleccione las operaciones o categorías (grupos funcionales BAPI) para el que desea generar un cliente de WCF y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas aparecen en la **agregar categorías y operaciones** cuadro. Puede seleccionar cualquier nodo que aparece en el **operaciones y categorías disponibles** cuadro. Si selecciona un nodo de categoría, se seleccionarán todas las operaciones disponibles en ese nodo y sus nodos secundarios.  
  
   > [!IMPORTANT]
   >  El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera una clase de cliente WCF única para cada objeto de negocios. Dependiendo de las categorías y las operaciones que seleccione, se puede generar más de una clase de cliente WCF. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
4. Para la mayoría de los escenarios son suficientes; las opciones de serialización predeterminado Sin embargo, si es necesario, puede controlar varios aspectos sobre el código generado y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
   1. Haga clic en **opciones avanzadas** para abrir el **opciones avanzadas** cuadro.  
  
   2. En el **opciones avanzadas** cuadro bajo **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si los métodos asincrónicos se generan para el cliente de WCF o deshabilitar la generación de un archivo de configuración.  
  
   3. En **serializador** selecciona el serializador que se debe usar.  
  
      La siguiente ilustración muestra el **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y ninguna otra opción que se ha seleccionado).  
  
      ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      Las opciones que se pueden configurar en el **opciones avanzadas** cuadro son equivalentes a algunas de las opciones disponibles al utilizar ServiceModel Metadata Utility Tool (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx). 
  
5. Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda el cliente de WCF de clase y código auxiliar en el directorio del proyecto para las categorías y operaciones seleccionadas. De forma predeterminada, también se guarda un archivo de configuración. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)