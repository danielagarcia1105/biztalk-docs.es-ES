---
title: "Cómo configurar el componente de canalización de validador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Validator [pipeline component]
- send pipelines, validating
- pipeline components, XML Validator
- receive pipelines, validating
ms.assetid: 3b3becaf-703c-4399-a5ed-e7082e31e6e9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 821ad6a1353c0aa29866fd36fe84a7ea6317690b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a>Cómo configurar el componente de canalización de validador XML
El componente de canalización de validador XML puede utilizarse en cualquier fase (excepto en desensamblar o ensamblar) tanto en una canalización de envío como de recepción.  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a>Para configurar las propiedades del componente de canalización de validador XML  
  
1.  Arrastre el componente de canalización de validador XML a la fase de validación de una canalización de recepción.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, configure lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Esquemas de documentos**|Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al documento. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md). Si no se hubiera especificado ningún esquema, la detección de esquemas en tiempo de ejecución se hará utilizando el espacio de nombres de destino del mensaje y la información de nombre del elemento raíz. **Nota:** recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para la **esquemas de documentos** propiedad. <br /><br /> Valor predeterminado: colección vacía|  
    |Procesamiento de intercambio recuperable|Cuando es "false" - indica que todo el intercambio se valida como una unidad (si se suspende los mensajes que contiene se produce un error, todo el intercambio).<br /><br /> Cuando es "true" - indica que los mensajes dentro de intercambio se extraen individualmente validador con posibilidad de que algunos se propaguen mediante la ruta de mensajería y otros se suspendan.<br /><br /> Para obtener más información sobre el procesamiento de intercambio recuperable, consulte [el procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md).|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de validador XML](../core/xml-validator-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)