---
title: Requisitos previos para las actividades de desarrollo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc79fd31e78581d98ecad34579958ff90f3b1e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006261"
---
# <a name="prerequisites-for-the-development-activities"></a>Requisitos previos para las actividades de desarrollo
Esta sección describe cómo preparar el entorno para completar los pasos descritos en las actividades de desarrollo que se incluyen como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Complete la configuración siguiente antes de intentar cualquiera de los procedimientos descritos en las actividades de desarrollo:  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a>Configurar el equipo para realizar los procedimientos de las actividades de desarrollo del Kit de herramientas de ESB de BizTalk  
  
1.  Instalar e implementar la aplicación de ejemplo de itinerario, la aplicación de ejemplo de resolución dinámica y la aplicación de ejemplo de varios servicios Web. Para obtener más información sobre cómo instalar e implementar estas aplicaciones, consulte [aplicaciones de ejemplo de BizTalk ESB Toolkit](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).  
  
2.  Ejecute la utilidad de editor UDDI.  
  
3.  En el equipo de desarrollo, en el Explorador de Windows, cree las rutas de acceso siguientes:  
  
    -   C:\HowTos  
  
    -   C:\HowTos\Itineraries  
  
    -   C:\HowTos\DropFolder  
  
    -   C:\HowTos\Out  
  
4.  Asegúrese de que la cuenta de servicio de BizTalk Server tiene **Control total** permisos para la estructura de directorios C:\HowTos.  
  
5.  Asegúrese de que la cuenta de servicio de Microsoft BizTalk Server tiene **escribir** permisos para C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out.  
  
6.  Copie el siguiente mensaje de prueba en la carpeta C:\HowTos:  
  
    -   C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.Xml  
  
7.  En la carpeta C:\HowTos, cree un acceso directo a la aplicación de cliente de prueba de itinerario que se encuentra en la siguiente ubicación:  
  
    -   C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB. Itinerary.Test\bin\Debug\ESB. Itinerary.Test.exe  
  
## <a name="create-the-visual-studio-solution"></a>Crear la solución de Visual Studio  
  
1.  En Visual Studio, en el menú archivo, seleccione **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, en el panel tipos de proyecto, haga clic en **Visual C#** y, a continuación, haga clic en **biblioteca de clases** en el panel Plantillas.  
  
3.  En el **nombre** , escriba **ItineraryLibrary**.  
  
4.  En el **ubicación** , escriba **C:\HowTos**.  
  
5.  Seleccione el **crear directorio para la solución** casilla de verificación.  
  
6.  En el **nombre de la solución** , escriba **patrones**y, a continuación, haga clic en **Aceptar** para crear la solución.  
  
7.  Eliminar el **Class1.cs** de archivos desde el **ItineraryLibrary** proyecto.