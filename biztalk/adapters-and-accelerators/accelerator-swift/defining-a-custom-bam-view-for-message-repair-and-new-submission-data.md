---
title: "Definir una vista BAM personalizadas para la reparación de mensajes y los nuevos datos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM views
- Message Repair and New Submission, BAM views
ms.assetid: 76a6e78d-9b11-4b43-a500-a9d7666ee468
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88ec7506a299476dccb6ef9f9d0125768ea80b6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="defining-a-custom-bam-view-for-message-repair-and-new-submission-data"></a>Definir una vista BAM personalizadas para la reparación de mensajes y los nuevos datos de envío
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]El programa de instalación proporciona un archivo de definición de BAM que define una actividad de negocio y una vista de negocio. Puede implementar el archivo de definición de BAM para utilizar esa vista, o puede crear una vista personalizada que se puede agregar al archivo de definición de BAM.  
  
 El archivo de definición de BAM es MrsrActivities.xml en  *\<unidad\>*: \Program Acelerador de BizTalk para SWIFT\BAMTracking. Define una actividad de mensaje y una vista RepairView. Para obtener más información acerca de la implementación MrsrActivities.xml utilizando el bm implementar utilidad, vea la Ayuda de BizTalk Server.  
  
 Crear la vista personalizada en la supervisión de vista de Asistente para actividad económica desde el libro BAM. Para obtener más información acerca de cómo crear una vista personalizada, vea "Crear una vista de BAM" en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ayuda de trabajador de información de BizTalk Server.  
  
 La actividad de mensaje en MrsrActivities.xml incluye los siguientes elementos que puede agregar a la vista personalizada:  
  
> [!NOTE]
>  Cuando se calculan las duraciones de BAM, se miden en unidades de un día (14,4 minutos =.01 día).  
  
|Elemento|Utilice|Tipo de elemento|  
|----------|---------|---------------|  
|Destino BIC|La dirección LT del receptor del mensaje (realizada a partir de los datos de bloque de encabezado de aplicación para los mensajes para SWIFT, o desde el 1 de bloque de mensajes de SWIFT donde el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] institución constituye el destino).<br /><br /> Estos datos siempre están presentes (de aplicación encabezado proporcionados por el destino LT SWIFTBound mensajes o desde básica LT de encabezado para los mensajes recibidos de SWIFT).|Datos económicos: Text|  
|Hora de finalización|La fecha y hora cuando la orquestación MRSRRepair completó el procesamiento del mensaje (MRSR_Completed o MRSR_Failed).<br /><br /> Estos datos están presentes sólo para los mensajes que se han completado el flujo de trabajo MRSR, es decir, han salido con **BTS. Operación** == **A4SWIFT_MRSRCompleted** o **A4SWIFT_MRSRFailed**.|Hito económico|  
|Referencia|El identificador de referencia exclusivo para este mensaje o la transacción asignado por la entidad emisora; toma del campo de 20 o 20C(SEME)|Datos económicos: Text|  
|Tipo de mensaje|El tipo de mensaje FIN o GPA.<br /><br /> Estos datos siempre están presentes (aplicación encabezado de entrada o salida de encabezado de la aplicación).|Datos económicos: Text|  
|Nuevo envío|Un indicador para saber si se trata de una nueva entrada (Y) o un mensaje que se originó en otro sistema u SWIFT (N).<br /><br /> Estos datos son solo aparece en los mensajes que se originaron en rol con capacidad de crear.|Datos económicos: Text|  
|Prioridad|La prioridad del mensaje SWIFT (N = normal, U = urgente, S = system).<br /><br /> Estos datos siempre están presentes.|Datos económicos: Text|  
|Hora de recepción|La fecha y hora cuando la orquestación MRSRRepair recibió por última vez el mensaje (de la fase anterior: vea a continuación).<br /><br /> Estos datos siempre están presentes.|Hito económico|  
|Remitente BIC|La dirección LT del remitente del mensaje (toman de 1 de bloque de mensajes para SWIFT donde el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] institución es el remitente, o de salida de encabezado de la aplicación para los mensajes de SWIFT).<br /><br /> Estos datos siempre están presentes (desde la dirección de LT encabezado básica para los mensajes de SWIFTBound o de salida de encabezado de la aplicación para los mensajes recibidos de SWIFT).|Datos económicos: Text|  
|Hora de envío|La fecha y hora en la orquestación MRSRRepair última envía el mensaje al sitio MRSR (para la fase actual).<br /><br /> Estos datos siempre están presentes, a menos que el mensaje está en curso en la orquestación.|Hito económico|  
|Start Time|La fecha y hora a la orquestación MRSRRepair inicialmente recibió el mensaje como un nuevo envío o como un mensaje de una interfaz (interno del sistema o SWIFT).<br /><br /> Estos datos siempre están presentes.|Hito económico|  
|Última etapa|El último paso completado en el flujo de trabajo (siempre la fase antes de que el mensaje es ahora)|Datos económicos: Text|  
|Estado|Puede ser:<br /><br /> -Completar (si se realiza correctamente)<br />-Restablecer y motivo (para restablecer si reinicia el flujo de trabajo de flujo de trabajo)<br />-No se pudo y motivo (si mensaje completado correctamente, es decir, se rechazan o agotó el tiempo).<br /><br /> Estos datos siempre están presentes.|Datos económicos: Text|  
|Department|El departamento seleccionado por la orquestación MRSRRepair según la directiva de departamento (depende de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] institución)|Datos económicos: Text|  
|Nombre de usuario|El nombre del usuario asociado con la fase anterior (consulte la fase anterior)|Datos económicos: Text|  
|Fase actual|El paso de flujo de trabajo a la que la orquestación MRSRRepair ha entregado el mensaje (por ejemplo, la Bandeja de entrada).<br /><br /> Estos datos están presentes, a menos que el mensaje ha completado la reparación de mensajes.|Datos económicos: Text|