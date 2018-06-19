---
title: Importación de esquemas en BizTalk Server Projects1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 719679dffa5bcffdeddcbcd889f847f147a705b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015451"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a>Importación de esquemas en proyectos de BizTalk Server
La información siguiente describe cómo importar esquemas en un proyecto de BizTalk Server.  
  
## <a name="importing-schemas"></a>Importación de esquemas  
  
#### <a name="to-import-schemas"></a>Para importar esquemas  
  
1.  En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y seleccione **agregar elementos generados**.  
  
2.  Haga clic en **agregar adaptador**y, a continuación, seleccione **abiertos**.  
  
3.  Seleccione el adaptador **, J.D. Edwards OneWorld XE**.  
  
4.  En la lista desplegable, seleccione el puerto **SSOSendToJD Edwards OneWorld XE**y, a continuación, haga clic en **siguiente**.  
  
     MyJ.D. Sistema lógico Edwards OneWorld XESSO aparece en el explorador (este sistema lógico se creó con la SSOSendToJ.D. Puerto Edwards OneWorld XE).  
  
5.  Expanda **myJ.D. Edwards OneWorld XESSO**.  
  
6.  Haga clic en el icono de flecha para mover el elemento (o simplemente arrástrelo) en el **transmisión** ventana y, a continuación, haga clic en **Aceptar**.  
  
     Los esquemas se agregan al proyecto SSOSchedule.  
  
7.  En el Explorador de soluciones, expanda **proyecto SSOSchedule**.  
  
8.  Haga clic en **BizTalk orchestration.odx**y, a continuación, haga clic en **eliminar**.  
  
9. En el Explorador de soluciones, haga doble clic en **GetList.odx** para inspeccionar la orquestación.  
  
## <a name="orchestration-types---port-types"></a>Tipos de orquestaciones: tipos de puertos  
  
-   **PortTypeIn / / solicitud:** SSOSchedule.myJ.D. Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeOut/Out/respuesta:** SSOSchedule.myJ.D. Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
-   **PortTypeInOut/InOut/solicitud:** SSOSchedule.myJ.D. Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeInOut/InOut/respuesta:** SSOSchedule.myJ.D. Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="orchestration-variables---messages"></a>Variables de orquestación: mensajes  
  
-   **MessageIn:** SSOSchedule.myJ.D. Edwards OneWorld XEsso_transmitService_3.method  
  
-   **MessageOut:** SSOSchedule.myJ.D. Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)