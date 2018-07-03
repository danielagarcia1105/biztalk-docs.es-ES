---
title: Usar el proveedor de datos para SAP con el complemento DDEX | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DDEX plug-in
- DDEX plug-in, Data Provider for SAP
- Data Provider for SAP, using with DDEX plug-in
ms.assetid: b16c8634-172a-4630-87ed-2073a75afdec
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 344467367e5745ab089c3f70be017759d22ba8b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970697"
---
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a>Usar el proveedor de datos para SAP con el complemento DDEX
Si decide instalar la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] junto con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] la instalación, el programa de instalación instala un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] complemento DDEX. Puede usar este complemento para examinar los objetos SAP mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Esta sección proporciona información sobre cómo usar el complemento DDEX.  
  
 Puede usar el complemento para establecer la conectividad con el sistema SAP, agregar las tablas del sistema SAP y agregar módulos de función desde el sistema SAP. Después de agregar las tablas y los módulos de función mediante el complemento de Visual Studio, los módulos de función y las tablas recién agregadas se reflejan en el archivo SAPDiscoveredObjects.xml. Para obtener más información acerca de este archivo, consulte [sobre el archivo SAPDiscoveredObjects.xml en SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Asegúrese de que eligió instalar los [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] junto con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación.  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a>Para conectarse a un sistema SAP mediante el complemento DDEX  
  
1. Inicie Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
2. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **vista** menú, haga clic en **Explorador de servidores**.  
  
3. En el **Explorador de servidores**, haga clic en **conexiones de datos**y seleccione **Agregar conexión**.  
  
4. En el **cambiar origen de datos** cuadro de diálogo desde el **origen de datos** cuadro, seleccione  **\<otros\>**.  
  
5. Desde el **proveedor de datos** lista desplegable, seleccione **.NET Framework Data Provider para mySAP Business Suite** y haga clic en **Aceptar**. El **Agregar conexión** abre el cuadro de diálogo.  
  
6. El **Agregar conexión** cuadro de diálogo enumera los parámetros de conexión diferente para conectarse a un sistema SAP. Una cadena de conexión típica para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere:  
  
   - Los parámetros de conexión para un tipo de conexión. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] es compatible con tipos de conexión A, B y D. Para conectarse a un sistema SAP debe proporcionar los parámetros de conexión para cualquier *una* de estos tipos de conexión. Por ejemplo, para el tipo de conexión A, debe proporcionar el nombre de host de servidor de la aplicación y el número del sistema.  
  
   - La información de inicio de sesión para conectarse a un sistema SAP como nombre de usuario y contraseña.  
  
     Para obtener más información acerca de la cadena de conexión para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [lea acerca de los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).  
  
     En el **Agregar conexión** diálogo cuadro, especifique:  
  
   - Los parámetros de conexión para cualquier tipo de una conexión.  
  
   - La información de inicio de sesión para conectarse a un sistema SAP.  
  
   - Si desea habilitar la depuración de GUI de SAP.  
  
   - Si desea utilizar el seguimiento de RFC SDK.  
  
     Haga clic en **Aceptar**. Se crea un nuevo nodo de conexión en el **conexiones de datos** nodo con el nombre del servidor que especificó en el paso anterior.  
  
7. Expanda el nodo de conexión nuevo para ver el **tablas** y **función módulos** nodos.  
  
    La siguiente ilustración muestra el Explorador de servidores una vez establecida la conexión.  
  
    ![Plug DDEX&#45;en para el proveedor de SAP ADO.NET](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a>Para agregar las tablas de un sistema SAP mediante el complemento DDEX  
  
1. En el **Explorador de servidores**, haga clic en el **tablas** nodo y haga clic en **buscar y agregar tablas**.  
  
2. En el **nombre de la tabla de búsqueda** texto, especifique una cadena de búsqueda para buscar tablas en el sistema SAP y haga clic en **búsqueda**.  
  
   > [!NOTE]
   >  El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] admite el uso de solo el carácter comodín de asterisco (*) para buscar las tablas.  
  
3. El **los resultados de búsqueda** cuadro muestra los nombres de tabla que cumplen los criterios de búsqueda.  
  
    ![Plug DDEX&#45;en el cuadro de diálogo de nombre de la búsqueda y agregar tablas](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")  
  
4. Active la casilla correspondiente a las tablas que desea agregar y haga clic en **agregar**. Para seleccionar todas las tablas, haga clic en **seleccionar todo**. Para borrar todas las selecciones, haga clic en **Borrar todo**.  
  
5. Un cuadro de diálogo le informa de que las tablas agregadas serían visibles después de actualizar el **tablas** nodo. Haga clic en **Aceptar**.  
  
6. Haga clic en el **tablas** nodo y seleccione **actualizar**. Las tablas seleccionadas aparecen bajo el **tablas** nodo. Haga clic en un nombre de tabla para ver las propiedades de tabla en la **propiedades** panel.  
  
7. Expanda un nombre de tabla para ver los campos de la tabla. Haga clic en un nombre de campo para ver las propiedades de campo en el **propiedades** panel.  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a>Para agregar las solicitudes de cambio de un sistema SAP mediante el complemento DDEX  
  
1. En el **Explorador de servidores**, haga clic en el **función módulos** nodo y haga clic en **buscar y agregar módulos de función**.  
  
2. En el **módulo de función de búsqueda** texto, especifique una cadena de búsqueda para buscar módulos de función en el sistema SAP y haga clic en **búsqueda**.  
  
   > [!NOTE]
   >  El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] admite el uso de solo el carácter comodín de asterisco (*) para buscar módulos funcionales.  
  
3. El **los resultados de búsqueda** cuadro enumera los módulos de función que cumplen los criterios de búsqueda.  
  
    ![Plug DDEX&#45;en el cuadro de diálogo Buscar y agregar módulos](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")  
  
4. Active la casilla correspondiente a los módulos de función que desea agregar y haga clic en **agregar**. Para seleccionar todos los módulos, haga clic en **seleccionar todo**. Para borrar todas las selecciones, haga clic en **Borrar todo**.  
  
5. Un cuadro de diálogo le informa de que los módulos de función agregada serían visibles después de actualizar el **función módulos** nodo. Haga clic en **Aceptar**.  
  
6. Haga clic en el **función módulos** nodo y seleccione **actualizar**. Los módulos de la función seleccionada aparecen bajo el **función módulos** nodo. Haga clic en un nombre de módulo de función para ver las propiedades en el **propiedades** panel.  
  
7. Expanda un nombre de módulo de función para ver los nodos para la importación, exportación, cambio y parámetros de la tabla.  
  
8. Expanda el **importar** nodo para enumerar los parámetros de la importación del módulo de función. De forma similar, expanda el **exportar** y **tablas** nodos para ver la lista de exportación y la tabla de parámetros para el módulo de función.  
  
## <a name="see-also"></a>Vea también  
 [Uso del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)