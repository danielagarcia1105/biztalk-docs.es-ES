---
title: Configurar propiedades del acuerdo de reserva o globales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c375d03-6f22-4a67-9eac-d8896de2f7ee
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eb693a17cad17eadaf0d005d12075dde30daa33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-global-or-fallback-agreement-properties"></a>Configuración de las propiedades de acuerdos globales o de respaldo
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa propiedades de acuerdo de reserva para procesar un mensaje si no descubre un acuerdo que resolver durante un intercambio. Las propiedades del acuerdo de reserva no se usan cuando el acuerdo es conocido y no se aplica a ningún acuerdo.  
  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje, intenta hacer coincidir la información del remitente para un acuerdo con la información del remitente en el mensaje. La información del remitente se encuentra en los elementos de datos ISA5 e ISA6 para mensajes X12 y en los elementos de datos UNB2.1 y UNB 2.2 para EDIFACT. La información del contrato está en las pestañas identificador en la pestaña del acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo. Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no descubre el acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará las propiedades del acuerdo de reserva para determinar el espacio de nombres, procesar el mensaje y enviar confirmaciones.  
  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía un mensaje, la canalización de envío de EDI determina el acuerdo que el mensaje resuelve mediante la coincidencia del puerto de envío que se suscribe al mensaje XML en el cuadro de mensajes con el puerto de envío asociado al acuerdo. Si el puerto de envío no está asociado con un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará las propiedades del acuerdo de reserva para procesar el mensaje para el envío.  
  
> [!NOTE]
>  La asociación del puerto de envío es solo un modo de resolver acuerdos. Para obtener más información acerca de la resolución del acuerdo para los mensajes salientes, vea [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración de X12 propiedades de acuerdo de reserva](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [Configuración de las propiedades del acuerdo de reserva de EDIFACT](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a>Vea también  
 [Rol de los acuerdos en el procesamiento de EDI](../core/the-role-of-agreements-in-edi-processing.md)