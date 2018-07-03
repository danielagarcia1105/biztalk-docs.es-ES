---
title: Esquemas EDI por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26da8036-8fe0-481e-b1e9-7f2e5b090768
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a25391fbc42b8e368a44f652ae691ff8bc2722dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999229"
---
# <a name="edi-batch-schemas"></a>Esquemas por lotes de EDI
Cuando BizTalk Server procesa un intercambio conservado, usa al menos tres esquemas:  

- Los esquemas por lotes (esquemas XML de intercambio), para validar el nodo raíz del intercambio por lotes conservado (X12_BatchSchema o Edifact_BatchSchema implementados en BaseArtifacts.dll).  

- Los esquemas de servicio de sobres, para validar los finalizadores y los encabezados de conjuntos de transacciones, grupos e intercambios (X12ServiceSchema o EdifactServiceSchema implementados en BaseArtifacts.dll). Para obtener más información, consulte [esquemas de Control y servicio EDI](../core/edi-service-and-control-schemas.md).  

- Esquemas de documentos, para cada tipo de documento del intercambio por lotes (implementados en su proyecto). Para obtener más información, consulte [esquemas de documentos EDI](../core/edi-document-schemas.md).  

  Los esquemas por lotes se usan en tiempo de ejecución para validar los intercambios por lotes de entrada y de salida que se están conservando. Los esquemas por lotes también se usan en tiempo de diseño para validar y generar instancias de mensajes.  

## <a name="batch-schemas-used-at-runtime"></a>Esquemas por lotes usados en tiempo de ejecución  
 Existen dos versiones canónicas de los esquemas por lotes: X12_BatchSchema.xsd para X12 codificación y EDIFACT_BatchSchema.xsd para la codificación EDIFACT. Estos esquemas son plantillas que incluyen el segmento de control. Estos esquemas tienen los siguientes nombres de raíz y espacios de nombres:  


|       esquema        |       Nodo raíz       |                    Espacio de nombres                     |
|---------------------|-----------------------|--------------------------------------------------|
|   X12_BatchSchema   |   X12InterchangeXML   | http://schemas.microsoft.com/Edi/X12_BatchSchema |
| Edifact_BatchSchema | EdifactInterchangeXML |     http://schemas.microsoft.com/Edi/Edifact     |

 El tipo de documento en la instancia XML generada por la canalización de recepción será una constante (\<Encoding\>_BatchSchema.xml) y hará referencia a este esquema canónico. Puede usar esta instancia en una asignación de una orquestación; no obstante, antes de hacerlo, tiene que modificar el tipo de documento y el espacio de nombres para realizar la asignación al esquema real necesario.  

 No tiene que especificar el esquema por lotes en tiempo de diseño en el proceso, ya que éste se implementa en BaseArtifacts.dll.  

## <a name="batch-schemas-in-the-schema-store"></a>Esquemas por lotes en el almacenamiento de esquema  
 Los esquemas por lotes que usa BizTalk Server en tiempo de ejecución para procesar lotes conservados se implementan en el ensamblado BaseArtifacts.dll. Éstos están disponibles de forma automática para el procesamiento en tiempo de ejecución. Edifact_BatchSchema y X12_BatchSchema también están disponibles en el almacén de esquemas de BizTalk en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI. Estos esquemas se usan sólo en tiempo de diseño para validar o generar el intercambio. No se necesita ningún esquema para la validación en la canalización de recepción o de envío en tiempo de ejecución.  

## <a name="see-also"></a>Vea también  
 [Esquemas EDI](../core/edi-schemas.md)   
 [Procesamiento de lotes de entrada](../core/processing-incoming-batches.md)