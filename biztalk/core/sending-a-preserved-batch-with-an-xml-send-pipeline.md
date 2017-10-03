---
title: "Enviar un lote conservado con un documento XML de canalización de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14bd61538398bb11967cbbe750a4fadc016a5168
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a>Enviar un lote conservado con una canalización de envío XML
Por lo general, se envía un lote conservado mediante una canalización de envío EDI. No obstante, se puede usar una canalización de envío XML para enviar un lote conservado. Puesto que el lote conservado que se genera y se coloca en el cuadro de mensajes a través de la canalización de recepción EDI se encuentra en formato XML, la canalización de envío XML debe pasar junto con el lote en formato XML.  
  
 Para enviar un lote conservado mediante la canalización de envío XML, se debe implementar un proyecto con el esquema por lotes aplicable y los esquemas de documento para cada tipo de mensaje en el intercambio. Además, también debe cambiar el espacio de nombres del esquema por lotes que implementa en el proyecto. Si no lo hace, el espacio de nombres del archivo XML por lotes conservado no se corresponderá con el espacio de nombres del esquema por lotes. Debe cambiar el espacio de nombres del esquema por lotes como se muestra en la siguiente tabla:  
  
|Para este tipo de codificación:|Cambie este espacio de nombres en el esquema por lotes:|En el siguiente espacio de nombres:|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|EDIFACT|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|X12|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 Esto no es un problema con el ensamblador EDI.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de lotes de EDI](../core/configuring-edi-batches.md)