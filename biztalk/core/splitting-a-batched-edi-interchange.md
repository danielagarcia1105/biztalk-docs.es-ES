---
title: Dividir un intercambio EDI por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29c79b06-cc88-4cc8-aa99-40f24a1bdcde
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441eafe79de57963dc1df5ac19334542f41a23d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="splitting-a-batched-edi-interchange"></a>Dividir un intercambio EDI por lotes
> [!NOTE]
>  Todas las opciones de interfaz de usuario mencionadas en este tema están disponibles en la **configuración de Host Local** página (**configuración del receptor** sección) de las fichas de acuerdo unidireccional en el **acuerdo Propiedades** cuadro de diálogo.  
  
 La recepción EDI canalización divide un lote de intercambio EDI entrante si ha configurado la **opción de procesamiento por lotes de entrada** propiedad de acuerdo a **dividir intercambio como conjuntos de transacciones**.  
  
 Cuando la canalización de recepción EDI divide un intercambio EDI por lotes entrante, crea un archivo XML para cada conjunto de transacciones/mensaje EDI. La canalización promociona todo el intercambio y los encabezados de grupo al contexto de cada división del conjunto de transacciones del intercambio. También promociona determinados encabezados de grupo y de intercambio específicos, como ISA6, GS1 y GS2, de forma que estos campos pueden usarse para el enrutamiento.  Puede enmascarar la información de seguridad en el encabezado seleccionando la **enmascare la información de autorización de seguridad/contraseña** propiedad.  
  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intenta dividir un intercambio en conjuntos de transacciones, cualquier error de algún campo de encabezado ISA (de ISA1 a ISA13) o UNB hará que el intercambio se rechace. Lo mismo sucede cuando el número de control de intercambio está duplicado, si la comprobación de un número de control de intercambio duplicado está habilitada en las propiedades del acuerdo o el acuerdo de reserva. Un error en otros campos de encabezado de intercambio (que no sea de ISA1 A ISA13 para el intercambio X12) o en los campos de encabezado de grupo no provocará un error en el procesamiento del intercambio.  
  
 Si **dividir intercambio como conjuntos de transacciones: suspender conjuntos de transacciones en caso de Error** está seleccionado en las propiedades del acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá el conjunto de transacciones si se produce un error. Si **dividir intercambio como conjuntos de transacciones: suspender intercambio en caso de Error** está seleccionada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá el intercambio.  
  
 Cada elemento del lote XML se enruta al cuadro de mensajes y procesado por los puertos de envío u orquestaciones que se suscriban al elemento por lotes. El orden de los conjuntos de transacciones en el intercambio no debe conservarse tras su procesamiento como mensajes divididos. En el caso de la recepción, los mensajes se procesarán en el orden de aparición en el intercambio, y se colocarán en el cuadro de mensajes en ese mismo orden, pero tendrá que utilizar convoyes o puertos de envío de entrega ordenada para mantener ese orden en el envío.  
  
 Si los elementos divididos desde un lote se van a incluir en un lote saliente, el componente de canalización BatchMarker promociona las propiedades necesarias. Para obtener más información, consulte [de procesamiento por lotes los mensajes EDI salientes](../core/batching-outgoing-edi-messages.md).  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento por lotes entrantes](../core/processing-incoming-batches.md)   
 [Procesamiento por lotes mensajes EDI salientes](../core/batching-outgoing-edi-messages.md)