---
title: "Desarrollar componentes de canalización personalizado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom]
- pipeline components [custom], about pipeline components
- pipeline components [custom], creating
- customizing, pipeline components
- pipeline interfaces
- IDisassemblerComponent
- pipeline interfaces, about pipeline interfaces
- creating, pipeline components [custom]
- IAssemblerComponent
- IComponent
- pipeline components [custom], customizing
- pipeline interfaces, interface types
- pipeline components [custom], interfaces
- pipeline components [custom], component types
ms.assetid: cce61e0d-f1e3-4ec2-b38c-7c6eaf83ac10
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723cd04a2a907fdb5d770975c27d47e1752d08ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-pipeline-components"></a>Desarrollar componentes de canalización personalizado
En esta sección, se describe cómo desarrollar un componente de canalización. Puede crear tres tipos de componentes de canalización: general, ensamblado y de desensamblado. Todos ellos pueden, de forma adicional, implementar la funcionalidad de búsqueda. Cada tipo de componente de canalización tiene una interfaz asociada que se debe implementar para que el componente para incluirse en el motor de mensajería de BizTalk; las interfaces de canalización que distinguen los tipos de componentes son **IComponent**, **IAssemblerComponent**, y **IDisassemblerComponent**. Para buscar componentes, debe implementar la **IProbeMessage** interfaz.  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contiene un componente de canalización de ejemplo al que puede hacer referencia al crear su propio componente. El componente de ejemplo demuestra cómo anexar datos al final de un mensaje y agregarlos al comienzo de éste. Para obtener más información sobre el componente de canalización de ejemplo, vea [CustomComponent (ejemplo de BizTalk Server)](../core/customcomponent-biztalk-server-sample.md).  
  
> [!CAUTION]
>  Si se hacen referencia a un componente de canalización personalizado desde una canalización de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede producirse un error de tiempo de compilación. Para corregir el error, cierre el Diseñador de canalizaciones y vuelva a abrirlo antes de efectuar la compilación. Como alternativa, puede quitar el componente y, a continuación, agregarlo.  
  
> [!IMPORTANT]
>  Al actualizar a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], asegúrese de que las variables de cadena de los componentes de canalización personalizados existentes no contienen caracteres de línea nueva, como es el caso de ‘\n’. De lo contrario, se producirá el error “nueva línea en constante” al compilar este componente en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Utilizar Interfaces de canalizaciones](../core/using-pipeline-interfaces.md)  
  
-   [Desarrollar un componente de canalización de General](../core/developing-a-general-pipeline-component.md)  
  
-   [Desarrollar un componente de canalización de ensamblado](../core/developing-an-assembling-pipeline-component.md)  
  
-   [Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [Desarrollar un componente de canalización de búsqueda](../core/developing-a-probing-pipeline-component.md)  
  
-   [Implementar un método Seek en un componente de canalización administrado de transmisión por secuencias](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [Utilizar los motores de análisis y serialización](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [Informar de errores de componentes de canalización](../core/reporting-errors-from-pipeline-components.md)  
  
-   [Implementar componentes de canalización](../core/deploying-pipeline-components.md)  
  
-   [Depurar canalizaciones personalizadas](../core/debugging-custom-pipelines.md)