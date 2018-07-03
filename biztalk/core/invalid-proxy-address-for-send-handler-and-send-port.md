---
title: Dirección de proxy no válido (para el puerto de envío y de controlador de envío) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccedd23e-7d44-4419-b519-e04511e1f176
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f509676b17a04fdbe0f0934225b5dc64546fed8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973549"
---
# <a name="invalid-proxy-address-for-send-handler-and-send-port"></a>Dirección de proxy no válida (para controlador de envío y puerto de envío)
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                             Dirección de proxy no válida: {0}                             |
  
## <a name="explanation"></a>Explicación  
 No proporcionó un controlador de envío WCF o un puerto de envío WCF con una dirección de proxy válida.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar una dirección de proxy.  
  
#### <a name="to-configure-a-proxy-address"></a>Para configurar una dirección de proxy  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **Proxy** ficha.  
  
9. Compruebe que la dirección del proxy en el **configuración de Proxy** sección está configurada correctamente.  
  
   Para obtener más información sobre los puertos de envío y los controladores de envío, vea los recursos siguientes:  
  
-   [Cómo configurar un puerto de envío WCF-WSHttp](../core/how-to-configure-a-wcf-wshttp-send-port.md)  
  
-   [Cómo configurar un puerto de envío WCF-BasicHttp](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)  
  
-   [Cómo configurar un controlador de envío WCF-BasicHttp](http://msdn.microsoft.com/library/18dcc616-4732-42f8-bd64-e55a5ebbaa49)  
  
-   [Cómo configurar un controlador de envío WCF-WSHttp](../core/how-to-configure-a-wcf-wshttp-send-handler.md)  
  
-   [Cómo configurar un puerto de envío WCF-Custom](../core/how-to-configure-a-wcf-custom-send-port.md)