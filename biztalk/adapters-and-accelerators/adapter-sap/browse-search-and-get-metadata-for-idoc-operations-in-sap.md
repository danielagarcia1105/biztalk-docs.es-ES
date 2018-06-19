---
title: Examinar, buscar y obtener los metadatos de las operaciones de IDOC en SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF client, generating for IDOC operations
- IDOCs, searching
- searching, IDOCs
- IDOCs, browsing
- browsing, IDOCs
- IDOC operations, generating schema for
- IDOC operations
ms.assetid: 44d05129-ce06-4a10-bf28-9d3519a02a7a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4c82ecf945e85c8e4c9b5f365c808598fcbbf3a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25967610"
---
# <a name="browse-search-and-get-metadata-for-idoc-operations-in-sap"></a>Examinar, buscar y obtener los metadatos de las operaciones de IDOC de SAP
Esta sección proporciona instrucciones sobre cómo examinar, buscar y recuperar los metadatos de SAP para las operaciones de IDOC con [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. La mayoría de las instrucciones que aparecen es los misma para toda la interfaz de usuario de tres. Siempre que se proporcionan procedimientos procede, independientes de la interfaz de usuario correspondientes.  
  
 Antes de realizar los pasos proporcionados en las secciones siguientes, debe disponer de:  
  
-   Crea un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto.  
  
-   Conectado al sistema SAP mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener instrucciones, consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) tenga en cuenta que, antes de conectarse a un sistema SAP para generar el esquema o un cliente WCF para IDOC, debe establecer ciertas propiedades de enlace.  
  
    -   GenerateFlatFileCompatibleIdocSchema  
  
    -   ReceiveIdocFormat  
  
    -   FlatFileSegmentIndicator  
  
     Estas propiedades controlan cómo se recuperan los metadatos para IDOC desde un sistema SAP. Para obtener más información acerca de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md). Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).  
  
## <a name="browsing-idocs-in-an-sap-system"></a>Exploración IDOC en un sistema SAP  
 Al examinar los metadatos que utilizan [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies de separan las operaciones para enviar y recibir IDOC desde un sistema SAP.  
  
-   **Enviar** y **recibir**. Los clientes de adaptador pueden usar estas operaciones para enviar y recibir IDOC desde un sistema SAP mediante un esquema fuertemente tipado. El adaptador de superficies de estas operaciones por separado para cada IDOC y están disponible en el nodo IDOC respectivo.  
  
-   **SendIdoc** y **ReceiveIdoc**. Los clientes de adaptador pueden usar estas operaciones para enviar y recibir IDOC desde un sistema SAP mediante un esquema débilmente tipada. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] sólo presenta uno **SendIdoc** y **ReceiveIdoc** operación para todos los IDOC. Estas operaciones están disponibles directamente en el **IDOC** nodo.  
  
 Realice los pasos siguientes para buscar IDOC en un sistema SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-browse-idocs-in-an-sap-system"></a>Para buscar IDOC en un sistema SAP  
  
1.  Conectar con un servidor SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectarse al sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3.  En el **seleccione una categoría de** cuadro, haga clic en el nodo IDOC para ver los tipos de mensajes IDOC en el **categorías y operaciones disponibles** cuadro. Como alternativa, también puede ver los tipos de mensaje IDOC, expanda el nodo IDOC.  
  
    > [!TIP]
    >  Puede ir directamente a la categoría "inmediata" nodos de subcategoría en el árbol, puede escribir el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccione una categoría de** cuadro. Por ejemplo, para saltar a la **ACC_BILLING** IDOC tipo de mensaje, mantener el foco en el **IDOC** nodo y, a continuación, escriba `ACC_BILLING`.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar el IDOC tipos de mensaje. El nodo raíz del IDOC también expone un **SendIdoc** opción para enviar los IDOC débilmente tipada al sistema SAP.  
  
     ![Examinar tipos de mensaje en un IDOC](../../adapters-and-accelerators/adapter-sap/media/3b8701c2-0530-4577-817c-92af0cd9a770.gif "3b8701c2-0530-4577-817c-92af0cd9a770")  
  
    > [!NOTE]
    >  Para ver un escenario de entrada, las superficies de nodo raíz IDOC un **ReceiveIdoc** operación recibir débilmente tipada IDOC.  
  
4.  Haga clic en los tipos de mensaje IDOC para ver el tipo de IDOC pertinente. La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] con el tipo IDOC en un IDOC determinado tipo de mensaje.  
  
     ![Examinar tipos IDOC](../../adapters-and-accelerators/adapter-sap/media/fee70ed2-74c1-4c91-b2fd-3d281a335145.gif "fee70ed2-74c1-4c91-b2fd-3d281a335145")  
  
5.  Haga clic en los tipos IDOC para ver las distintas versiones de un tipo de IDOC. La siguiente ilustración muestra la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] con las versiones de un determinado tipo IDOC.  
  
     ![Buscar versiones de un tipo de IDOC](../../adapters-and-accelerators/adapter-sap/media/35603fac-ff48-40b1-bb51-bd0548715cd3.gif "35603fac-ff48-40b1-bb51-bd0548715cd3")  
  
6.  Haga clic en la versión de un tipo IDOC para ver las operaciones admitidas en ese tipo IDOC. La siguiente ilustración muestra la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] con la operación admitida en una versión específica del tipo IDOC.  
  
     ![Buscar operaciones para un tipo de IDOC](../../adapters-and-accelerators/adapter-sap/media/f37624b4-f1f2-4d44-8708-01eb51a2d2a7.gif "f37624b4-f1f2-4d44-8708-01eb51a2d2a7")  
  
## <a name="searching-idocs-in-an-sap-system"></a>Buscar IDOC en un sistema SAP  
 Al buscar los metadatos para IDOC en un sistema SAP mediante [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   Admite caracteres comodín en la expresión de búsqueda.  
  
-   Permite la búsqueda inmediatamente debajo del nodo en el que se realiza la operación de búsqueda.  
  
 En la tabla siguiente se enumera los caracteres especiales que se pueden usar para buscar y su interpretación por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|+ (más)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, A + coincide con AB, CA, AD|  
|* (asterisco)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un * encuentra una, AB, ABC.|  
  
 Para obtener más información acerca de los caracteres especiales admitidos por el adaptador, vea [exponer la configuración del adaptador como una propiedad de enlace mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md).
  
 Realice los pasos siguientes para buscar IDOC en un sistema SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-search-idocs-in-an-sap-system"></a>Para buscar IDOC en un sistema SAP  
  
1.  Conectar con un servidor SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si buscarán las operaciones entrantes o salientes con el adaptador.  
  
3.  En el **seleccione una categoría de** cuadro, haga clic en el nodo IDOC.  
  
    > [!IMPORTANT]
    >  Puede buscar IDOC en el nivel de raíz.  
  
4.  En el **búsqueda en la categoría** texto cuadro, escriba una expresión de búsqueda para buscar un tipo específico de mensaje IDOC. Por ejemplo, para buscar IDOC que tienen "MATMAS" en sus nombres, escriba * MATMAS\* en el cuadro de texto.  
  
5.  Haga clic en el botón con el icono de flecha derecha para iniciar la búsqueda. Una vez completada, la búsqueda del **categorías y operaciones disponibles** cuadro muestra el IDOC que cumplen los criterios de búsqueda.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar el IDOC resultado de búsqueda.  
  
     ![Buscar IDOC en un sistema SAP](../../adapters-and-accelerators/adapter-sap/media/tut1-lesson3-step3-idocsearch.gif "Tut1-Lesson3-Step3-IDOCSearch")  
  
## <a name="generating-schema-for-biztalk-projects"></a>Generar el esquema para los proyectos de BizTalk  
 Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para los artefactos SAP seleccionados. Una vez examinar y buscar los artefactos que desea invocar, puede generar esquema para los artefactos y enviar mensajes, que se ajuste al esquema, al sistema SAP.  
  
> [!NOTE]
>  Puede seleccionar nodos de categoría para devolver todas las operaciones en el subárbol de esa categoría, por ejemplo, puede seleccionar un tipo IDOC (para generar el esquema para todas las versiones del IDOC en ese grupo) o seleccione una versión específica de IDOC para generar el esquema para que solo la versión de IDOC. Para obtener más información acerca de los nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
#### <a name="to-retrieve-metadata-for-idocs"></a>Para recuperar los metadatos para IDOC  
  
1.  Conectar con un servidor SAP mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Vea [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si va a realizar operaciones entrantes o salientes mediante el adaptador.  
  
3.  En el **seleccione una categoría de** cuadro, haga clic en el tipo de mensaje IDOC o el tipo IDOC para el que desea generar los metadatos.  
  
4.  En el **categorías y operaciones disponibles** , seleccione el tipo IDOC o las operaciones admitidas para el que desea generar los metadatos y haga clic en **agregar**. Las operaciones o tipos IDOC seleccionados se muestran en la **agregar categorías y operaciones** cuadro.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] enumerar el IDOC seleccionados.  
  
     ![Recuperar metadatos para IDOC](../../adapters-and-accelerators/adapter-sap/media/d9765c62-68b2-4313-9292-9265ab095e2e.gif "d9765c62-68b2-4313-9292-9265ab095e2e")  
  
     Si desea generar esquema para varias operaciones, puede haber algunas definiciones de elemento duplicado entre estos esquemas que puede producir un error en la compilación del proyecto de BizTalk. Por ejemplo, considere un escenario donde se genere el esquema para una operación "Op1". El esquema para "Op1" contiene un parámetro de tipo de datos complejo "CT1". Después de generar el esquema para "Op1" cerrar la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y vuelva a abrirlo para generar el esquema para otra operación "Op2". Supongamos que "Op2" también contiene un parámetro de tipo de datos complejo "CT1". Después de salir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y compilar el proyecto, se producirán errores de compilación porque el tipo de datos complejo "CT1" se define dos veces en distintos archivos XSD. En estas situaciones, se recomienda lo siguiente:  
  
    -   Generar esquema para todas las operaciones en una única ejecución de [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Esto garantiza que la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera una única definición para el tipo de datos complejo "CT1".  
  
    -   Si desea generar esquema para varias operaciones entre distintas ejecuciones del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], asegúrese de seleccionar la **generar tipos de esquema únicos** casilla de verificación para que los archivos XSD generados contienen espacios de nombres únicos para los más complejos tipo de datos "CT1".  
  
5.  Haga clic en **Aceptar**. El archivo de esquema se guarda con una extensión .xsd en la misma ubicación que el proyecto IDOC.  
  
    > [!NOTE]
    >  Si utilizas [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], de forma predeterminada, los archivos se crean con la convención de nomenclatura "SAPBinding\<n\>.xsd", donde ' n ' puede ser 1, 2, etc. según el número de archivos de esquema creado. Como alternativa, puede proporcionar un nombre personalizado para los archivos de esquema, escriba un nombre en el **prefijo de nombre de archivo** cuadro de texto. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] ahora crea archivos de esquema con la convención de nomenclatura \<prefijo de nombre de archivo\>\<n\>.xsd.  
  
    > [!NOTE]
    >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace (un archivo XML) que contiene las propiedades de enlace que especificó al generar el esquema para una operación y la acción SOAP para invocar la operación. Puede importar este archivo de enlace en la consola de administración de BizTalk Server para crear un puerto de WCF-Custom con el URI, propiedades de enlace de conexión y establece la acción SOAP. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).  
  
6.  En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="generating-a-wcf-client-for-idoc-operations-using-the-add-adapter-service-reference-plug-in"></a>Generar un cliente WCF para operaciones de IDOC mediante el Agregar referencia de servicio de adaptador complemento  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el código de cliente WCF para enviar IDOC a un sistema SAP o un contrato de servicio WCF para recibir IDOC desde un sistema SAP.  
  
#### <a name="to-generate-a-wcf-client-or-a-wcf-service-contract-for-idocs"></a>Para generar un cliente WCF o un contrato de servicio WCF para IDOC  
  
1.  En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], desde el **seleccione el tipo de contrato** lista desplegable, seleccione el tipo de contrato en función de si se va a realizar operaciones de (enviar idoc) salientes o entrante (idoc receptor).  
  
2.  En el **seleccione una categoría de** , expanda la **IDOC** nodo y, a continuación, examinar o buscar el tipo de mensaje IDOC o el tipo IDOC que desea enviar o recibir.  
  
3.  En el **categorías y operaciones disponibles** , seleccione el tipo IDOC o las operaciones admitidas para el que desea generar un cliente de WCF (o un contrato de servicio WCF) y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas se muestran en la **agregar categorías y operaciones** cuadro. Puede seleccionar cualquier nodo que aparece en el **categorías y operaciones disponibles** cuadro. Si selecciona un nodo de categoría, se agregarán todas las operaciones disponibles en ese nodo y sus nodos secundarios.  
  
    > [!IMPORTANT]
    >  El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera una clase de cliente WCF únicos (o contrato de servicio WCF) para cada tipo IDOC. Dependiendo de las categorías y las operaciones que seleccione, se puede generar más de una clase de cliente WCF. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
4.  Para la mayoría de los escenarios, las opciones de serialización predeterminadas son suficientes; Sin embargo, si es necesario, puede controlar varios aspectos sobre el código que se genera y el tipo de serializador que se utiliza. Para establecer estas opciones:  
  
    1.  Haga clic en **opciones avanzadas** para abrir el **opciones avanzadas** cuadro.  
  
    2.  En el **opciones avanzadas** cuadro en **elegir las opciones para el proxy generado**, seleccione las opciones que desee. Por ejemplo, puede seleccionar si los métodos asincrónicos se generan para el cliente de WCF o deshabilitar la generación de un archivo de configuración.  
  
    3.  En **serializador** seleccionar el serializador que se debe usar.  
  
     La siguiente ilustración muestra la **opciones avanzadas** cuadro con las selecciones predeterminadas (**automática** está seleccionada para el serializador y no hay otras opciones están seleccionadas).  
  
     ![Opciones avanzadas de la configuración predeterminada del cuadro](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     Las opciones que puede configurar en el **opciones avanzadas** cuadro equivalen a algunas de las opciones disponibles cuando se usa la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe). Para obtener más información acerca de estas opciones, consulte [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
5.  Haga clic en **Aceptar**. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] guarda la clase de cliente WCF (o la interfaz de servicio WCF) y código auxiliar para las operaciones y categorías que ha seleccionado en el directorio del proyecto. De forma predeterminada, también se guarda un archivo de configuración. Se generan archivos ligeramente diferentes para las operaciones de entrada y salidas; Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)