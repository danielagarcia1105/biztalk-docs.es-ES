---
title: ApplicationAdapter | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9b876b-cd37-4e24-a476-186adc155ac0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee9d04f98da5e9b8aa1faba81f32fe5ec37d23b9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963194"
---
# <a name="applicationadapter"></a>ApplicationAdapter
El ejemplo ApplicationAdapter muestra cómo enviar notificaciones desde los procesos públicos y privados (servicio de respuesta o iniciador) cuando se recibe un mensaje. Puede personalizar el ejemplo con cualquier funcionalidad adicional que desee.  
  
 El ejemplo ApplicationAdapter muestra cómo implementar el `IApplicationAdapter` de la interfaz para la `ApplicationAdapter1` clase. Esta clase incluye dos métodos, `BeginNotify` y `Notify`. Los parámetros para cada clase de la categoría del mensaje, nombre de la entidad de origen, nombre de la entidad de destino, código de proceso de interfaz de socio (PIP), Id. de instancia PIP y PIP versión.  
  
 Establecer el ApplicationAdapter para un acuerdo si se escribe el nombre del ensamblado y el nombre de clase en el **General** ficha del acuerdo en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console. El archivo .dll de adaptador de aplicación se ejecuta con las mismas credenciales que el servicio de host de BizTalk.  
  
 Si cambia el ejemplo ApplicationAdapter o cualquier variable de entorno externo que depende el ejemplo ApplicationAdapter, reinicie el servicio de host de BizTalk que hospeda el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso público.  
  
 Se encuentra en el código de ejemplo de ApplicationAdapter \< *unidad*\>: \Program Files\ BizTalk \<versión\> Accelerator for RosettaNet\SDK\ApplicationAdapter\\.  
  
## <a name="demonstrates"></a>Demostraciones  
 El ejemplo ApplicationAdapter muestra cómo se notifica a los procesos privados de servicio de respuesta que el proceso público ha recibido un mensaje. La notificación indica la categoría del mensaje, el nombre de la entidad de origen, el nombre de la entidad de destino, el código PIP, la versión PIP y el identificador de instancia PIP. Puede enviar esta notificación para una acción o un mensaje de respuesta.  
  
 El `BeginNotify` y `Notify` métodos funcionan como se indica a continuación:  
  
1.  El proceso público de servicio de respuesta recibe un mensaje.  
  
    > [!NOTE]
    >  Los siguientes pasos también son aplicables para el escenario en el que el iniciador público recibe un mensaje de respuesta desde el servicio de respuesta.  
  
2.  Si la validación por la canalización de recepción y el proceso público y el adaptador de validación, si procede, se realiza correctamente, el público de servicio de respuesta procesa llamadas el `BeginNotify` método en la `ApplicationAdapter` clase. Este método notifica a los procesos privados de servicio de respuesta que el proceso público ha recibido el mensaje nuevo y guarda el mensaje en la base de datos de cuadro de mensajes.  
  
3.  El proceso público de servicio de respuesta envía un mensaje de señal al iniciador.  
  
4.  El proceso público de servicio de respuesta envía el contenido del servicio de mensajes al proceso privado de servicio de respuesta.  
  
5.  El proceso privada del servicio de respuesta coloca el mensaje en la tabla MessagesToLOB de la base de datos BTARNDATA.  
  
6.  Las llamadas de procesos privados del servicio de respuesta el `Notify` método en la `ApplicationAdapter` clase para enviar el mensaje final notificar hacia el proceso público de servicio de respuesta. El proceso público de servicio de respuesta debe recibir el mensaje de notificar al final del proceso se complete correctamente. En caso contrario, el mensaje se suspende.  
  
> [!NOTE]
>  Puede usar el `Notify` mensaje para indicar que la aplicación de línea de negocio (LOB) que está esperando el mensaje en la tabla MessagesToLOB. Como pronto el sistema de alertas de la aplicación de LOB, la aplicación de LOB puede recuperar el mensaje de esa tabla.  
  
## <a name="to-implement-this-sample"></a>Para implementar este ejemplo  
 Para implementar el ejemplo ApplicationAdapter, debe agregar el adaptador de la aplicación para el acuerdo.  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a>Para agregar el adaptador de la aplicación a un acuerdo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] **BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, Haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración**.  
  
2.  En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y haga clic en **contratos**.  
  
3.  Haga doble clic en el acuerdo al que desea agregar el adaptador de la aplicación.  
  
4.  En el **aplicación adaptador** cuadro, haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de **nombre de ensamblado**, desplácese a la ubicación que contiene el ensamblado de adaptador de la aplicación, seleccione el archivo .dll adecuado y, a continuación, haga clic en **abiertos**.  
  
5.  Haga clic en la flecha hacia abajo para **nombre de la clase**, seleccione la clase de adaptadores de aplicación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)