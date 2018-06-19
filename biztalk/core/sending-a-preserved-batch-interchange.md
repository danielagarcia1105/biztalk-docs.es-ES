---
title: Enviar un intercambio por lotes conservado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9bc2207-e34d-4d06-a224-bd7f8e498c27
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5813bb4881535290422e2ba01d20d4370f4e604
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974850"
---
# <a name="sending-a-preserved-batch-interchange"></a>Enviar intercambios por lotes conservados
Cuando la canalización de envío EDI procesa un intercambio por lotes conservado, toma el intercambio como una unidad entera. Normalmente, vuelve a utilizar los segmentos de sobre (control) existentes para la creación del intercambio de EDI, en vez de aplicar un sobre basado en el acuerdo. Esto se produce cuando el **opción de procesamiento por lotes de entrada** propiedad está establecida en **conservar intercambio: suspender intercambio en caso de Error** o **conservar intercambio: suspender conjuntos de transacciones en Error**.  
  
## <a name="schema-validation"></a>Validación de esquemas  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] valida el sobre de un lote conservado mediante los esquemas por lotes y los esquemas de servicio. El esquema por lotes se utiliza para validar el nodo raíz del mensaje conservado; los esquemas de servicio se utilizan para validar los finalizadores y los encabezados de conjuntos de transacciones, grupos e intercambios. Para obtener más información acerca de los esquemas por lotes, vea [esquemas de EDI por lotes](../core/edi-batch-schemas.md). Para obtener más información sobre los esquemas de servicio, consulte [servicio EDI y esquemas de Control](../core/edi-service-and-control-schemas.md).  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] valida los documentos de un intercambio por lotes mediante los esquemas de documentos del proyecto.  
  
## <a name="send-side-processing"></a>Procesamiento de envío  
 Cuando el Ensamblador EDI procesa un intercambio conservado, normalmente utiliza los mismos encabezados de intercambio, grupo y conjunto de transacciones que ya existían en el intercambio por lotes cuando se recibió.  
  
-   Para los intercambios de X12, los valores de propiedad en varias páginas en la ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo (que determinan cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creará los encabezados ISA, GS y ST de un tipo de salida intercambio) normalmente no se aplican.  
  
-   Para los intercambios EDIFACT, normalmente se utilizan los valores UNA de las propiedades del acuerdo. El segmento UNA es opcional en un mensaje codificado en EDIFACT aunque es necesario para serializar un intercambio por lotes conservado. Si no hay ningún valor para el segmento UNA en la instancia XML, se utilizarán los valores predeterminados de la propiedad para el componente de canalización de envío. Si las propiedades del componente de canalización de envío no tienen valor, se suspenderá el mensaje XML intermediario del lote conservado.  
  
-   Si promociona la propiedad de contexto `EDI.PopulateInterchangeValues` a "True" en el intercambio que se va a conservar (en un componente personalizado), el Ensamblador EDI del puerto de envío rellenará todos los encabezados de intercambio, grupo y conjunto de transacciones con los valores establecidos en las propiedades del acuerdo.  
  
-   Si promociona la propiedad de contexto `EDIOverride.OverrideEdiHeader` a "True" en el intercambio antes de que sea procesado por la canalización de envío, puede invalidar los valores de sobre para el documento de salida estableciendo los valores de propiedad de contexto de `EDIOverride` adecuados. Para obtener más información, consulte [reemplazar los encabezados EDI](../core/overriding-edi-headers.md).  
  
 Para un intercambio conservado sin errores, el Ensamblador conservará la secuencia de conjuntos de transacciones en un grupo del intercambio y la secuencia de grupos en el intercambio.  
  
> [!NOTE]
>  Puede enviar un lote conservado con una canalización de envío XML. Sin embargo, para ello es necesario que cambie el espacio de nombre del esquema por lotes. Para obtener más información, consulte [enviar un lote conservado con una canalización de envío XML](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md).  
  
## <a name="error-processing"></a>Procesamiento de errores  
 La canalización de envío EDI reconoce un intercambio de EDI por lotes como un lote conservado debido a una etiqueta reservada en el XML. Esta etiqueta, ya sea \<X12InterchangeXml\> o \<EdifactInterchangeXml\>, se aplica al XML EDI canalización de recepción.  
  
 Las siguientes casos especiales se aplican los conjuntos de transacción suspendidos en caso de error:  
  
-   Si todos los conjuntos de transacciones en un grupo son no válidos, la canalización de envío EDI incluirá segmentos de control de grupo en el EDI generado, aunque el grupo no contendrá conjuntos de transacciones (porque se habrán quitado). Los totales de pie de página del grupo se actualizan en cero. Los segmentos de control de intercambio no cambian.  
  
-   Si todos los conjuntos de transacciones en un intercambio son no válidos, los segmentos de control de intercambio se seguirán incluyendo en el intercambio de EDI generado, aunque este intercambio no contendrá conjuntos de transacciones (porque se habrán quitado). Esto sería un intercambio vacío.  
  
-   Si los segmentos de control de grupo o de control de intercambio son no válidos, no se generará un intercambio codificado en EDI. Se creará un registro en el visor de eventos para indicar que se rechazó el intercambio.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento por lotes mensajes EDI salientes](../core/batching-outgoing-edi-messages.md)