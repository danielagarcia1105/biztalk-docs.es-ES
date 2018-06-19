---
title: Componente de canalización de ensamblador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22348b61ca32567190fa99e103fe536f5199af58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289492"
---
# <a name="xml-assembler-pipeline-component"></a>Componente de canalización de ensamblador XML
El componente de canalización de ensamblador XML combina la serialización y el ensamblado XML en un componente. Su primera función es transferir propiedades del contexto del mensaje de vuelta a los sobres y documentos.  
  
 Las siguientes acciones tienen lugar en el componente de ensamblador XML después de recibir un lote de mensajes para formar un intercambio:  
  
1.  El ensamblador crea el sobre mediante la especificación de sobre definida.  
  
2.  El componente coloca las propiedades del contenido en las instancias de mensaje mediante los XPaths predefinidos, codificados como anotaciones en los esquemas XSD asociados al mensaje.  
  
3.  El componente anexa el mensaje al sobre.  
  
4.  El componente coloca las propiedades del contenido en el sobre mediante los XPaths predefinidos, codificados como anotaciones en los esquemas XSD asociados a los sobres.  
  
> [!NOTE]
>  El componente de canalización de ensamblador XML no llena los campos de atributos que faltan, pero llena los campos de elementos vacíos cuando los campos son opcionales pero no tienen valores predeterminados o fijos.  
  
 Para obtener información acerca de cómo configurar el componente de canalización de ensamblador XML, vea [cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Codificación de caracteres en el componente de canalización de ensamblador XML](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [Instrucciones de procesamiento en el componente de canalización de ensamblador XML](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [Mensajes desconocidos en el componente de canalización de ensamblador XML](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [Elementos Set de información XML en el componente de canalización de ensamblador XML](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [Obligatoriedad de estructura del documento en el componente de canalización de ensamblador XML](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)