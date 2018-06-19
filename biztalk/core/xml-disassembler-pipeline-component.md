---
title: Componente de canalización de desensamblador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3346cdbfeed14e933039d7866e174c833f17212e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289876"
---
# <a name="xml-disassembler-pipeline-component"></a>Componente de canalización del desensamblador de XML
El componente de canalización de desensamblador XML combina el análisis y desensamblado en un componente. Sus funciones principales son:  
  
-   Quitar sobres.  
  
-   Desensamblar el intercambio.  
  
-   Promover las propiedades de contenido desde los niveles de documentos individuales y de intercambio hasta el contexto del mensaje.  
  
 Las siguientes acciones tienen lugar en el componente de desensamblador XML después de recibir un sobre:  
  
1.  El desensamblador analiza el sobre utilizando los esquemas del sobre asociados estáticamente con el componente en tiempo de diseño o dinámicamente al determinar los esquemas de sobres a partir del tipo de mensaje en tiempo de ejecución. El esquema se utiliza para comprobar la estructura del sobre durante su análisis. Si no se define la estructura del sobre, se encuentra de forma recursiva gracias a la utilización del espacio de nombres y nombre base del nodo raíz para buscar los esquemas.  
  
2.  El componente del desensamblador analiza todos los documentos que hay dentro del sobre. Para cada documento, se crea un objeto de mensaje de BizTalk con su propio contexto donde se copian todas las propiedades promovidas del sobre y del documento en sí. El componente saca las propiedades del contenido del sobre y las instancias de mensaje mediante los XPaths predefinidos y codificados como anotaciones en los esquemas XSD asociados con el sobre y el mensaje. Los esquemas de sobres así como los de los documentos individuales están asociados con el componente de desensamblador en el Diseñador de canalizaciones.  
  
 El desensamblador XML sólo procesa datos en la parte del cuerpo del mensaje. Por lo tanto, sólo se pueden promover las propiedades de la parte del cuerpo. Los valores datetime de los campos asociados con las propiedades que se pueden promover se convierten a UTC cuando se produce una promoción de propiedades. Las partes que no sean del cuerpo se copian en el mensaje de salida sin ningún cambio.  
  
> [!NOTE]
>  El componente de canalización de desensamblador XML fuerza la conversión actual de todas las propiedades datetime a UTC antes de alcanzar el almacén de mensajes. BizTalk Server utiliza un tipo datetime de SQL internamente, el cual no tiene información sobre la zona horaria. Si genera una propiedad datetime en una orquestación y, a continuación, intenta utilizarla para correlación con mensajes posteriores, es posible que no funcione correctamente, porque el componente de canalización del desensamblador XML la convertirá en respuesta a UTC y Microsoft SQL Server no tendrá posibilidad de identificar los campos de tiempo original y de respuesta porque son idénticos. De forma similar, puede encontrar discrepancias al visualizar los datos de seguimiento de instancias de servicio y eventos de mensajes.  
  
 Para obtener información acerca de cómo configurar el componente de canalización de desensamblador XML, vea [cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Elementos Set de información XML en el componente de canalización de desensamblador XML](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [Mensajes desconocidos en el componente de canalización de desensamblador XML](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [Validación de documentos en el componente de canalización de desensamblador XML](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [Obligatoriedad de estructura del documento en el componente de canalización de desensamblador XML](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [Codificación de caracteres en el componente de canalización de desensamblador XML](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [Tutorial: Utilizar sobres XML (básicos)](../core/walkthrough-using-xml-envelopes-basic.md)