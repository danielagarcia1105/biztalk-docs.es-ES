---
title: 'Paso 1: Preparar el Tutorial de programadores de la interfaz EDI | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9be1bddf-d673-4054-87f5-0205b8b5cc0d
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0823f42f5f7963d1c70f1b2d7e16ed595d01bd83
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972981"
---
# <a name="step-1-prepare-for-the-edi-interface-developer-tutorial"></a>Paso 1: Preparar el Tutorial de programadores de la interfaz EDI
![Paso 1 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  
  
 El tutorial de programadores de la interfaz EDI se ejecuta en un único equipo. Para preparar el tutorial, debe instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como se describe en [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5). También debe agregar una referencia a la aplicación EDI de BizTalk  
  
> [!NOTE]
>  Para que funcione este tutorial, se debe ejecutar en una plataforma con IIS 7.5 o IIS 8.  
  
 Los archivos necesarios para el tutorial de programadores de la interfaz EDI están ubicados en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial. Las carpetas y archivos necesarios para el tutorial son los siguientes:  
  
|Carpeta\Archivo|Finalidad|  
|------------------|-------------|  
|\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln|El archivo de solución que se utiliza en Visual Studio para crear este escenario de mensajería|  
|\SDK\EDI Interface Developer Tutorial\keyfile.snk|El archivo de clave de ensamblado especificado para el archivo de solución|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt|El archivo de mensaje de ejemplo (versión 4010 850) que utiliza para probar la solución|  
|\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm|La asignación de BizTalk que convierte los datos del mensaje 850 al formato necesario según el sistema de pedidos.|  
|\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp|La canalización de envío que procesa el mensaje de prueba para enviar el mensaje al sistema de pedidos.|  
|\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\X12_00401_850.xsd|Esquema 850 para el mensaje de prueba.|  
\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM|La carpeta en la que se recibe el mensaje 850 entrante desde Fabrikam|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem|La carpeta a la que se envía el mensaje 850 saliente, que representa la aplicación de servidor del sistema de pedidos.|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997|La carpeta a la que se envía la confirmación 997, que representa a Fabrikam|  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-add-reference-to-the-biztalk-edi-application"></a>Procedimiento para agregar una referencia a la aplicación EDI de BizTalk  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **aplicaciones** nodo, haga clic en la aplicación que desea usar con EDI, por ejemplo, BizTalk Application 1. Seleccione **agregar**y, a continuación, haga clic en referencias.  
  
2. En el **Agregar referencia de aplicación** cuadro de diálogo, seleccione **aplicación EDI de BizTalk**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Compilar e implementar el ensamblado Inbound_EDI, tal como se describe en [paso 2: actualizar e implementar la solución del Tutorial](../core/step-2-update-and-deploy-the-tutorial-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Tutorial de desarrollador de la interfaz EDI](../core/tutorial-2-edi-interface-developer-tutorial.md)