---
title: "Ubicación de recepción de solicitud-respuesta transaccional no se admite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34de32b338a78b598941d4e828c1a0b736dde4e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a>La ubicación de recepción de solicitud-respuesta transaccional no es compatible
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|La ubicación de recepción de solicitud-respuesta transaccional no es compatible.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que la transacción se estableció para habilitarse para una ubicación de recepción de solicitud-respuesta de WCF. BizTalk no admite las transacciones para una ubicación de recepción de solicitud-respuesta debido a la base de datos de cuadro de mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Para los adaptadores de WCF estándar, vaya al código que configura la ubicación de recepción de solicitud-respuesta. Asegúrese de que el **EnableTransaction** elemento de los datos XML para el **TransportTypeData** propiedad de la **ITransportInfo** interfaz se establece en **False** .  
  
 Para los adaptadores de WCF-Custom:  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
9. Asegúrese de que la propiedad transactionFlow está establecida en **False**.