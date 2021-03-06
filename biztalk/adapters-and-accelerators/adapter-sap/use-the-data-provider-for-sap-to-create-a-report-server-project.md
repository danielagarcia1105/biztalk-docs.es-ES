---
title: Usar el proveedor de datos para SAP para crear un proyecto de servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f57155b386af979f1da52d39d062aff171203b5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008213"
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a>Usar el proveedor de datos para SAP para crear un proyecto de servidor de informes
Debe crear un servidor de informes del proyecto, mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], para generar informes de los datos disponibles en un sistema SAP. Este tema proporciona instrucciones sobre cómo crear un proyecto de servidor de informes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que ha instalado el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] durante la instalación de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación. Para obtener más información acerca de [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, consulte la Guía de instalación disponible en \< *unidad de instalación*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
### <a name="to-create-a-report-server-project"></a>Para crear un proyecto de servidor de informes  
  
1. Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y cree un proyecto de servidor de informes. Para crear un proyecto de servidor de informes, haga lo siguiente:  
  
   1.  Haga clic en el **archivo** menú, haga clic en **New**y, a continuación, haga clic en **proyecto**.  
  
   2.  En el **nuevo proyecto** cuadro de diálogo desde el **tipos de proyecto** lista, seleccione **proyectos de Business Intelligence**. Desde **plantillas instaladas de Visual Studio** lista, seleccione **Report Server Project**.  
  
   3.  Especifique un nombre y ubicación del proyecto y haga clic en **Aceptar**. Este tema, especifique el nombre del proyecto como `SAP_ Report`.  
  
2. Agregar un nuevo origen de datos:  
  
   1. En el Explorador de soluciones, haga clic en **orígenes de datos compartidos**y haga clic en **Agregar nuevo origen de datos**.  
  
   2. En el **origen de datos compartido** cuadro de diálogo el **General** ficha, especifique un nombre para el origen de datos. Este tema, especifique el nombre como `SAPDataSource`.  
  
   3. Desde el **tipo** lista, seleccione **proveedor de datos para SAP**.  
  
   4. En el **cadena de conexión** , especifique la cadena de conexión para el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]. Para obtener información sobre la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] cadena de conexión, consulte [lea acerca de los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).  
  
       ![Crear un origen de datos](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")  
  
      > [!NOTE]
      >  Puede elegir especificar las credenciales como parte de la cadena de conexión o especificarlos tal como se describe en el paso siguiente.  
  
   5. En el **credenciales** ficha, elija uno de los siguientes y, a continuación, haga clic en **Aceptar**:  
  
      |Use|Para|  
      |--------------|----------------|  
      |**Utilizar un nombre de usuario y una contraseña específicos**|Especifique un nombre de usuario y una contraseña para conectarse al sistema SAP.|  
      |**Pedir credenciales**|Escriba las credenciales para el sistema SAP mientras se genera el informe. **Nota:** las credenciales que especifique para esta opción reemplazará las credenciales, si se especifica como parte de la cadena de conexión.|  
      |**Sin credenciales**|Elija esta opción si va a proporcionar el nombre de usuario y la contraseña como parte de la cadena de conexión.|  
  
      > [!NOTE]
      >  No se admite el modo de autenticación de Windows para los proyectos de servidor de informes.  
  
3. Agregar un nuevo informe:  
  
   1. En el Explorador de soluciones, haga clic en **informes**y, a continuación, haga clic en **Agregar nuevo informe**.  
  
       Esto inicia al Asistente para informes.  
  
   2. Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.  
  
   3. En el **Seleccionar origen de datos** diálogo cuadro, elija el **origen de datos compartido** opción, seleccione el **SAPDataSource** creado en el paso anterior y, a continuación, haga clic en  **Siguiente**.  
  
   4. Si eligió el **pedir credenciales** opción para especificar las credenciales de usuario al crear el origen de datos, un **escribir credenciales de origen de datos** aparece el cuadro de diálogo. Especifique el nombre de usuario y la contraseña para conectarse al sistema SAP y, a continuación, haga clic en **Aceptar**.  
  
       Si elige cualquier otra opción para especificar las credenciales, el asistente avanza al paso siguiente.  
  
   5. En el **diseñar la consulta** diálogo cuadro, especifique una cadena de consulta que se usa para generar un informe. Por ejemplo:  
  
      ```  
      SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
      ```  
  
       Esta consulta recuperará los dos registros principales de la tabla KNA1 donde el nombre1 es el nombre que se especifican al generar el informe.  
  
       Haga clic en **Siguiente**.  
  
   6. En los cuadros de diálogo siguientes puede diseñar el formato en el que desea que aparezca el informe. Si desea usar el formato predeterminado, haga clic en **finalizar >>&#124;**  para ir directamente a la **finalizar** cuadro de diálogo.  
  
   7. En el **completando el Asistente para** cuadro de diálogo, especifique un nombre para el informe, revise el resumen y, a continuación, haga clic en **finalizar**. Este tema, especifique el nombre del informe como `SAPReport`.  
  
      Ahora puede ver el informe. Para obtener instrucciones sobre cómo ver el informe, vea [ver los informes de SAP](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md).  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos para SAP con SSRS](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)