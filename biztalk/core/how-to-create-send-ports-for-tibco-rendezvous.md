---
title: "Cómo crear puertos de envío para TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- ports, send
- send ports, creating
ms.assetid: 0c8d9fdc-b273-4876-9f93-b5a85539a3c1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b6e7dbb1a3b32979c94ec1af9483bd9fcb7cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a>Creación de puertos de envío para TIBCO Rendezvous
Siga estos pasos para crear un puerto de envío mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
    6.  Haga clic en **configurar** para configurar el puerto de envío.  
  
4.  En el **propiedades de transporte de TIBCO Rendezvous** diálogo cuadro, realice lo siguiente:  
  
    1.  Especifique las propiedades.  
  
         No tiene que establecer la información de inicio de sesión.  
  
    2.  En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema TIBCO Rendezvous.  
  
    3.  Para **usar SSO**, seleccione **Sí**.  
  
    4.  Haga clic en **Aceptar**.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de envío TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)