---
title: 'Paso 8: Ver los mensajes en las bases de datos BTARN | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- loopback tutorial, viewing messages
- databases, viewing messages
ms.assetid: c549670c-4428-483c-906c-eff163ddef9a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56563473e5865e9b94edefd76e9f230f8cd37f67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998451"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a>Paso 8: Ver los mensajes en las bases de datos BTARN
En este paso, utilice SQL Query Analyzer para ver los mensajes de la línea de negocio (LOB) almacenados en el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] base de datos para comprobar que su escenario de bucle invertido funciona correctamente.  
  
 Después de la aplicación LOB utilidad genera un mensaje LOB y lo envía a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], ocurre lo siguiente para el iniciador (inicio) y el Respondedor (asociado):  
  
 Flujo de trabajo de iniciador  
  
- SubmitRNIF envía el mensaje LOB a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.  
  
- El adaptador de SQL de recepción ubicación recoge el mensaje y lo entrega a la base de datos de cuadro de mensajes. El adaptador de SQL recoge un mensaje en un tiempo de ejecución el `GetMessagesFromLOB` procedimiento almacenado.  
  
- El iniciador privado toma el mensaje de la base de datos de cuadro de mensajes y lo coloca nuevamente a la base de datos de cuadro de mensajes con propiedades de contexto promocionadas adicionales.  
  
- El iniciador público toma el mensaje de la base de datos de cuadro de mensajes en función del filtro de suscripción.  
  
- El HTTP del puerto de envío recoge el mensaje con la canalización RNIFSend basándose en las suscripciones. Guarda el mensaje en la tabla MessageStorageOut de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] archivar la base de datos para el no rechazo y, a continuación, envía el mensaje a través de la página RNIFSend.aspx.  
  
- La página RNIFSend.aspx recibe el mensaje codificado con MIME con variables de cadena de consulta que incluyen el destino final del mensaje (URL de organización de asociado).  
  
  Flujo de trabajo de servicio de respuesta  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía el mensaje RNIF a la página de trabajo RNIFReceive.aspx donde se quita el contenedor de descodificación MIME. El mensaje se identifica como sincrónico o asincrónico y luego se reenvían a la sincrónica o asincrónica de recepción ubicación (RNIF_Sync_Receive o RNIF_Async_Receive).  
  
- La recepción HTTP de ubicación primero guarda el formato del mensaje en la tabla MessageStorageIn de rechazo de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archivar base de datos. Ubicación de recepción de HTTP, a continuación, se descodifica, descifra (para RNIF 2.0), valida en su firma, separa las partes del mensaje XML, autoriza en función de la firma y, a continuación, lo coloca en la base de datos de cuadro de mensajes con las propiedades promocionadas correctas  
  
- El servicio de respuesta pública toma las partes del mensaje en función de suscripción y, a continuación, se valida y procesa el mensaje según el estándar RNIF correcto. El elemento de contenido de servicio coloca el mensaje en la base de datos de cuadro de mensajes con las propiedades de contexto correcta.  
  
- El código SQL puerto de envío recoge el mensaje en función del filtro de suscripción. A continuación, guarda el mensaje en la tabla MessagesToLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.  
  
> [!NOTE]
>  En el lado de servicio de respuesta, el servicio de respuesta pública es responsable de generar la confirmación de recepción o de la señal de excepción al iniciador. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no guarda el mensaje de señal en la tabla MessagesFromLOB. Esto es porque la aplicación de LOB no genera el mensaje de señal. El mensaje de acción continuará hasta el Respondedor privado, y [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] lo guarda en la tabla MessagesToLOB.  
> 
> [!NOTE]
>  Para PIP de doble acción, la línea de negocio en el lado de servicio de respuesta es responsable de generar un mensaje de respuesta. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] lo coloca en la tabla MessagesFromLOB pasen por el mismo proceso que el proceso del lado del iniciador. En este caso, el proceso público del iniciador en el lado del iniciador volver envía una señal de confirmación de recepción o de excepción para el mensaje de respuesta.  
  
### <a name="to-view-messages-in-the-btarn-databases"></a>Para ver los mensajes en las bases de datos BTARN  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft SQL Server \<versión\>** y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2. En conectar al cuadro de diálogo de servidor, haga clic en **Connect**.  
  
   > [!NOTE]
   >  En el panel Explorador de objetos, compruebe que se ha iniciado el Agente SQL Server. Si no, haga clic en **del Agente SQL Server**y haga clic en **iniciar**.  
  
3. En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
4. En la ventana de consulta en blanco, escriba lo siguiente:  
  
   ```  
   use BTARNArchive  
   SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
   SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
   use BTARNData  
   SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
   ```  
  
5. En Microsoft SQL Server Management Studio, haga clic en **Execute**.  
  
   Verá un mensaje de acción en la tabla MessagesFromLOB y, si ejecuta la consulta a intentarlo en unos minutos (tiempo puede variar según la configuración del sistema), verá dos mensajes generados en la tabla MessagesToLOB con valores de MessageCategory de AsyncAckSignal (25) y AsyncAction (10).  
  
## <a name="see-also"></a>Vea también  
 [Bucle invertido](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)   
 [Tutorial de bucles invertidos](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
