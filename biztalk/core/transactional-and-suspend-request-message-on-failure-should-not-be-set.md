---
title: Opción de transacciones &quot;transaccional&quot; y la opción de control de errores &quot;suspender el mensaje de solicitud en caso de error&quot; deben no establecerse ambas como false | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8c47e364fccdb310167e56c6556423c2d4b39d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278932"
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a>Opción de transacciones &quot;transaccional&quot; y la opción de control de errores &quot;suspender el mensaje de solicitud en caso de error&quot; deben no establecerse ambas como false
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|La opción de transacciones "Transaccional" y la opción de control de errores "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False, ya que el mensaje podría perderse. Establezca una o ambas opciones como true.|  
  
## <a name="explanation"></a>Explicación  
 En el adaptador de WCF-NetMsmq, las opciones de **transaccional** y **suspender el mensaje de solicitud en caso de error** deben no establecerse ambas como false (desactivada). Se puede perder el mensaje si el envío de mensaje con el error no se deshace como una transacción, mientras el mensaje no está suspendido y almacenado en el cuadro de mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para comprobar la configuración del adaptador.  
  
#### <a name="to-verify-adapter-settings"></a>Para comprobar la configuración del adaptador  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
9. En el **transacciones** sección, determine si **transaccional** está activada.  
  
10. Haga clic en el **mensajes** ficha.  
  
11. Determinar si **suspender el mensaje de solicitud en caso de error** está activada.  
  
    > [!NOTE]
    >  Estos pasos únicamente se aplican a ubicaciones de recepción.