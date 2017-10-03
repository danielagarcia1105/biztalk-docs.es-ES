---
title: "Canalizaciones de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines, message flow
- send pipelines, about send pipelines
- messages, message flow
- send pipelines, stages
- pipelines, send pipelines
- messages, send pipelines
ms.assetid: c963b2d8-3b2b-4575-8105-c750deae8189
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef08909dbc47e11f5c9fecae6f65e01dbe79441b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="send-pipelines"></a>Canalizaciones de envío
La ilustración que aparece a continuación muestra el flujo de trabajo de procesamiento de mensajes aunque se centra en la canalización de envío.  
  
 ![Diagrama de flujo de trabajo para procesar un mensaje. ] (../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")  
Representación del flujo de trabajo de procesamiento de mensajes.  
  
 La canalización de envío se ocupa del procesamiento de documentos antes de enviarlos a su destino final. La canalización de envío recibe un mensaje y crea otro para enviarlo.  
  
 Puede crear una nueva canalización de envío o puede usar una de las canalizaciones de envío de dos valores predeterminados incluidas en BizTalk Server, el acceso directo enviar canalización y la canalización de envío XML.  
  
 De forma predeterminada, la canalización de envío consta de tres fases: preensamblar, ensamblar y codificar. Este tema contiene consideraciones de diseño para rellenar estas fases.  
  
> [!NOTE]
>  Una canalización de envío puede no crear ningún mensaje cuando se agrega un componente que se esté utilizando a la canalización.  
  
## <a name="pre-assemble-stage"></a>Fase de preensamblado  
  
-   Esta fase es un marcador de posición para componentes personalizados que deberían realizar alguna acción en el mensaje antes de serializarlo.  
  
-   Esta fase se ejecuta una vez para cada mensaje.  
  
-   Esta fase puede contener entre cero y 255 componentes.  
  
-   Se ejecutan todos los componentes de esta fase.  
  
## <a name="assemble-stage"></a>Fase de ensamblado  
  
-   Los componentes de esta fase son los responsables de ensamblar o serializar el mensaje y convertirlo en XML o desde XML.  
  
-   Esta fase acepta un componente o ninguno.  
  
-   Se ejecutan todos los componentes de esta fase.  
  
## <a name="encode-stage"></a>Fase de codificación  
  
-   Esta fase se utiliza para los componentes que codifican o cifran el mensaje.  
  
    -   Si la firma del mensaje es necesaria, el componente de codificador de MIME/SMIME o un componente de codificación predeterminado se sitúa en esta fase.  
  
-   Esta fase se ejecuta una vez para cada mensaje.  
  
-   Esta fase puede contener entre cero y 255 componentes.  
  
-   Se ejecutan todos los componentes de este archivo.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones de recepción](../core/receive-pipelines.md)   
 [Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md)   
 [Tipos de canalizaciones](../core/types-of-pipelines.md)   
 [Canalizaciones predeterminadas](../core/default-pipelines.md)   
 [Plantillas de canalización](../core/pipeline-templates.md)   
 [Componentes de canalización](../core/pipeline-components.md)   
 [Tipos de componentes de canalización](../core/types-of-pipeline-components.md)