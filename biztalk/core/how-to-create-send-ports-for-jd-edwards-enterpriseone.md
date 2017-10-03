---
title: "Cómo crear puertos de envío para JD Edwards EnterpriseOne | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send ports
- send ports, creating [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], send ports
- send ports, JD Edwards EnterpriseOne adapters
- creating, send ports [JD Edwards EnterpriseOne adapters]
ms.assetid: 687f9207-ad3e-41ea-8640-5b9b6efbc14e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a3e8d2d3e8e1db230a03d9c4a0351d3a0f8394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a>Creación de puertos de envío para JD Edwards EnterpriseOne
Mediante[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree un puerto de envío.  
  
### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**y, a continuación, expanda el aplicación para la que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío** y haga clic en **New**y, a continuación, haga clic en **puerto de petición-respuesta estático**.  
  
4.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    -   En el **nombre** , escriba un nombre de puerto de envío (por ejemplo, `SendToJDE`).  
  
    -   Desde el **tipo** lista desplegable, seleccione **JDEdwards**.  
  
    -   Desde el **controlador de envío** lista desplegable, seleccione la dirección del controlador de envío.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de JD Edwards EnterpriseOne envío](../core/creating-jd-edwards-enterpriseone-send-handlers.md)