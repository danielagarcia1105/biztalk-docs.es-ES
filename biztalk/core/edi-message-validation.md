---
title: "Validación del mensaje EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21439969bc8e23b5b9901077c14a98128aa64c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-validation"></a>Validación de mensajes EDI
Los datos EDI se transmiten como archivos delimitados (sin etiquetas de autodescripción) y, por tanto, las reglas de codificación fuerzan las reglas de formato estrictas para garantizar que la aplicación de destino puede analizar de forma correcta y consumir la información para el procesamiento descendente.  
  
 La canalización de recepción EDI y la canalización de envío EDI en las funcionalidades EDI y AS2 de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realizan una serie de validaciones. Siempre se llevan a cabo algunos de estos procesos. Otros se realizan si se habilitan en las propiedades de acuerdo o en el esquema. Para obtener más información acerca de cómo configurar la validación, consulte [cómo validar un EDI del intercambio está configurado](../core/how-validation-of-an-edi-interchange-is-configured.md).  
  
 La validación de un intercambio EDI implica diferentes tipos de validaciones, como se describe en los siguientes temas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo configurar la validación de un intercambio EDI](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [Validación estructural de EDI](../core/edi-structural-validation.md)  
  
-   [Validación de propiedades de acuerdo](../core/agreement-properties-validation.md)  
  
-   [Validación de tipo (elemento de datos) de EDI](../core/edi-type-data-element-validation.md)  
  
-   [Validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md)  
  
-   [Validación de esquemas](../core/schema-validation2.md)  
  
-   [Campo de segmento validación cruzada](../core/cross-field-segment-validation.md)