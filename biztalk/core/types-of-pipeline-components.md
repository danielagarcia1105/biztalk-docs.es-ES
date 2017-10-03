---
title: "Tipos de componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: pipelines, components
ms.assetid: 9b493758-6b0f-4223-94bb-8f077ee735a9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ba18aed137380f6b3d491ad52cfcee94bf111a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="types-of-pipeline-components"></a>Tipos de componentes de canalización
Se incluyen tres tipos de componentes de canalización [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]: general, ensamblado y de desensamblado. Cualquiera de los tres tipos también puede implementar funcionalidad de búsqueda. En este tema se describen los tipos de componentes y las fases en las que suelen utilizarse.  
  
## <a name="general"></a>General  
 Los componentes generales toman un mensaje, lo procesan y producen un mensaje o ninguno.  
  
 Los componentes de descodificador de MIME/SMIME, de codificador de MIME/SMIME, de resolución de entidades y de validador son los componentes generales incluidos. Puede que necesite crear componentes generales personalizados para comprimir el tamaño de un mensaje antes de enviarlo, o utilizar un mensaje mientras espera información adicional para procesarlo.  
  
 Los componentes generales deben situarse en las fases de descodificación, codificación, preensamblado, ResolveParty o validación.  
  
 Para obtener información acerca de cómo desarrollar componentes de canalización generales, vea [desarrollar un componente de canalización generales](../core/developing-a-general-pipeline-component.md).  
  
## <a name="assembling"></a>De ensamblado  
 Los componentes de ensamblado tienen numerosas responsabilidades en la preparación del mensaje que se va a enviar. En primer lugar, el componente convierte el mensaje XML en el formato XML o no XML nativo apropiado del mensaje, según el tipo de ensamblador y propiedades establecidos en el esquema. Además, los componentes de ensamblado ensamblan y ajustan el mensaje en un sobre o agregan un encabezado o un finalizador (o ambos) al mensaje. Durante el ensamblado, algunas propiedades se desplazan del contexto del mensaje al cuerpo del documento o al sobre.  
  
 Los componentes de ensamblado predeterminados son los componentes de ensamblador de BizTalk Framework, el de ensamblador de archivo sin formato y el de ensamblador XML.  
  
 Los componentes de ensamblado deben situarse en la fase de ensamblado de las canalizaciones de envío.  
  
 Para obtener información sobre cómo desarrollar componentes de canalización de ensamblado, consulte [desarrollar un componente de canalización de ensamblado](../core/developing-an-assembling-pipeline-component.md).  
  
## <a name="disassembling"></a>De desensamblado  
 Los componentes de desensamblado completan muchas tareas de preparación del mensaje para dividirlo en documentos individuales según el sobre y los esquemas de documentos para utilizarlos en el servidor BizTalk Server. En primer lugar, el componente de desensamblado puede convertir mensajes no XML en su equivalente XML, lo que es necesario para que el servidor BizTalk Server los procese. A continuación, el mensaje se desensambla en mensajes individuales que pueden enviarse a orquestaciones separadas. El mensaje se desensambla quitando el sobre, dividiendo el mensaje en documentos individuales según el sobre y los esquemas de mensaje y, seguidamente, desplazando las propiedades desde el sobre hasta los contextos de mensajes individuales. Asimismo, algunas propiedades pueden promocionarse desde el cuerpo del mensaje hasta el encabezado. El esquema determina las propiedades promocionadas.  
  
 El componente de desensamblado también debe establecer la propiedad de tipo de mensaje, que se utiliza para enrutar los mensajes adecuadamente. La propiedad de tipo de mensaje es Namespace#RootElement del cuerpo del mensaje. Otras propiedades, como el tipo de contenido y el juego de caracteres, se establecen como parte de la propiedad de contexto.  
  
 Los componentes de desensamblado predeterminados incluidos en el servidor BizTalk Server son los componentes de desensamblador de BizTalk Framework, el de desensamblador de archivo sin formato y el de desensamblador XML.  
  
 Los componentes de desensamblado deben utilizarse en la fase de desensamblado de las canalizaciones de recepción.  
  
 Para obtener información sobre cómo desarrollar componentes de canalización de desensamblado, consulte [desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md).  
  
## <a name="probing"></a>Búsqueda  
 Un componente de búsqueda comprueba la primera parte del mensaje para ver si está en un formato que el componente entiende. Si el formato es conocido, se entrega todo el mensaje a este componente para que lo procese.  
  
 Para obtener información sobre el desarrollo de sondeo, componentes de canalización, consulte [desarrollar un componente de canalización de sondeo](../core/developing-a-probing-pipeline-component.md).  
  
## <a name="see-also"></a>Vea también  
 [Tipos de canalizaciones](../core/types-of-pipelines.md)   
 [Canalizaciones predeterminadas](../core/default-pipelines.md)   
 [Plantillas de canalización](../core/pipeline-templates.md)   
 [Componentes de canalización](../core/pipeline-components.md)   
 [Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md)