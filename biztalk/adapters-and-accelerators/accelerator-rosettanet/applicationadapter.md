---
title: ApplicationAdapter | Microsoft Docs
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
ms.openlocfilehash: 8b7a754b044fb12bf7cec9fed0e5455e6192c072
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974933"
---
# <a name="applicationadapter"></a>ApplicationAdapter
El ejemplo ApplicationAdapter muestra cómo enviar notificaciones desde los procesos públicos y privados (servicio de respuesta o iniciador) cuando reciba un mensaje. Puede personalizar el ejemplo con cualquier funcionalidad adicional que desee.  
  
 El ejemplo ApplicationAdapter muestra cómo implementar la `IApplicationAdapter` interfaz a la `ApplicationAdapter1` clase. Esta clase incluye dos métodos, `BeginNotify` y `Notify`. Los parámetros para cada clase de la categoría de mensaje, nombre de la entidad de origen, nombre de la entidad de destino, código de proceso de interfaz de socio (PIP), Id. de instancia PIP y versión de PIP.  
  
 Establecer el ApplicationAdapter para un acuerdo, escriba el nombre del ensamblado y el nombre de clase en el **General** ficha del acuerdo en el Microsoft® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console. El archivo .dll de adaptador de aplicación se ejecuta bajo las mismas credenciales que el servicio de host de BizTalk.  
  
 Si cambia el ejemplo ApplicationAdapter o cualquier variable de entorno externo que depende el ejemplo ApplicationAdapter, reinicie el servicio de host de BizTalk que hospeda el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso público.  
  
 Se encuentra en el código de ejemplo ApplicationAdapter \< *unidad*\>: \Program Files\ BizTalk \<versión\> Acelerador para RosettaNet\SDK\ApplicationAdapter\\.  
  
## <a name="demonstrates"></a>Demostraciones  
 El ejemplo de ApplicationAdapter muestra cómo notificar a los procesos Respondedor privado que el proceso público ha recibido un mensaje. La notificación indica la categoría del mensaje, el nombre de la entidad de origen, el nombre de la entidad de destino, el código PIP, la versión PIP y el identificador de instancia PIP. Puede enviar esta notificación para una acción o un mensaje de respuesta.  
  
 El `BeginNotify` y `Notify` métodos funcionan como sigue:  
  
1.  El proceso público del Respondedor recibe un mensaje.  
  
    > [!NOTE]
    >  Los siguientes pasos también son aplicables para el escenario en el que el iniciador público recibe un mensaje de respuesta desde el servicio de respuesta.  
  
2.  Si la validación por la canalización de recepción y el proceso público y el adaptador de validación, si procede, se realizó correctamente, el público del Respondedor procesa llamadas la `BeginNotify` método en el `ApplicationAdapter` clase. Este método notifica el proceso privado del servicio de respuesta que el proceso público ha recibido el mensaje nuevo y guarda el mensaje en la base de datos de cuadro de mensajes.  
  
3.  El proceso público del Respondedor envía un mensaje de señal al iniciador.  
  
4.  El proceso público del Respondedor envía el contenido del servicio de mensaje para el proceso privado del Respondedor.  
  
5.  El proceso privado del Respondedor coloca el mensaje en la tabla MessagesToLOB de la base de datos BTARNDATA.  
  
6.  Las llamadas de proceso privado del Respondedor del `Notify` método en el `ApplicationAdapter` clase para enviar el mensaje final notificar hasta el proceso público del Respondedor. El proceso público del Respondedor debe recibir el mensaje de notificar al final para el proceso se complete correctamente. En caso contrario, el mensaje se suspende.  
  
> [!NOTE]
>  Puede usar el `Notify` mensaje para indicar que la aplicación de línea de negocio (LOB) que está esperando el mensaje en la tabla MessagesToLOB. Como pronto el sistema de alertas de la aplicación de LOB, la aplicación de LOB puede recuperar el mensaje de esa tabla.  
  
## <a name="to-implement-this-sample"></a>Para implementar este ejemplo  
 Para implementar el ejemplo ApplicationAdapter, debe agregar el adaptador de aplicación para el acuerdo.  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a>Para agregar el adaptador de aplicación a un acuerdo  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, señale Microsoft **BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Consola de administración**.  
  
2. En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y haga clic en **acuerdos**.  
  
3. Haga doble clic en el acuerdo al que desea agregar el adaptador de aplicación.  
  
4. En el **aplicación adaptador** cuadro, haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de **nombre del ensamblado**, desplazarse a la ubicación que contiene el ensamblado de adaptador de aplicación, seleccione el archivo .dll adecuado y, a continuación, haga clic en **abierto**.  
  
5. Haga clic en la flecha hacia abajo para **nombre de la clase**, seleccione la clase de adaptador de aplicación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)