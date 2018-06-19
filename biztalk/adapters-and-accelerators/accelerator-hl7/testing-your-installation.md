---
title: Comprobación de la instalación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fc94930ba5ff0851114e36d728ee7f3ffb73ab
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961068"
---
# <a name="testing-your-installation"></a>Comprobación de la instalación
Puede configurar su [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] instalación para las pruebas manualmente ejecutando el tutorial to-end o ejecutando el programa tutorial-to-end. Para practicar con el programa, haga clic en el **iniciar Tutorial** botón durante la instalación o ejecutar EndToEndTutorial.exe en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\ Carpeta Tutorial de extremo a extremo (después de ejecutar la instalación y configuración). Cualquiera de estas acciones automatizadas llevará a cabo los mismos pasos de instalación que debe realizar manualmente mediante la ejecución de todo el tutorial. El programa tutorial-to-end hace lo siguiente:  
  
-   Implementa esquemas de confirmación y MSH  
  
-   Implementa los esquemas comunes de versión 2.3.1  
  
-   Implementa esquemas ADT  
  
-   Crea el Tutorial_1WayReceive puerto de recepción  
  
-   Crea la Tutorial_MLLPReceive ubicación de recepción  
  
-   Crea el Tutorial_BTAHL7PickUp puerto de recepción  
  
-   Crea la Tutorial_FileReceiveLoc ubicación de recepción  
  
-   Crea el puerto de envío Tutorial_sendAck_ADT  
  
-   Crea el puerto de envío Tutorial_sendMsg_RX  
  
-   Crea el puerto de envío Tutorial_BTAHL7Drop  
  
-   Crea el puerto de envío Tutorial_MLLPSend  
  
-   Crea la entidad Tutorial_ADTSystem  
  
-   Crea la entidad Tutorial_RXSystem  
  
-   Crea la entidad Tutorial_HISystem  
  
-   Reinicia el servicio de BizTalk  
  
 Si ha ejecutado el programa de tutorial de extremo a extremo, puede quitar una instancia de prueba para HL7 en una carpeta predefinida. La canalización de recepción asociada a la carpeta recoge el mensaje y lo procesa. En función de los filtros, una canalización de envío enruta el documento a la carpeta de destino. Este simple "redondeo" ejercicios de los bloques de creación básicos de la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) del motor y confirma la instalación.  
  
### <a name="to-test-your-installation"></a>Para probar la instalación  
  
1.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para la carpeta Tutorial HL7\SDK\End-to-End.  
  
2.  Haga clic en el **TutorialSampleInstance.txt** de archivos y, a continuación, haga clic en **copia**.  
  
3.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End Carpeta BTAHL7PickUp.  
  
4.  Haga clic en la carpeta y, a continuación, haga clic en **pegar**.  
  
5.  Usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a la \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End Carpeta BTAHL7Drop.  
  
     Puede comprobar si la instalación fue correcta si la instancia procesada aparece en el **Tutorial_BTAHL7Drop** carpeta como \< *Guid*\>.txt.  
  
 Continúe con el paso siguiente, [preparando para utilizar el Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).