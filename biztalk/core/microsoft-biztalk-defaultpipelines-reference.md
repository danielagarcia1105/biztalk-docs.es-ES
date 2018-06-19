---
title: Referencia de Microsoft.BizTalk.DefaultPipelines | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines
- PassThruTransmit pipelines
- XMLReceive pipelines
- pipelines, XMLTransmit
- Pipeline Designer
- pipelines, XMLReceive
- pipelines, about pipelines
- PassThruReceive pipelines
- XMLTransmit pipelines
- namespaces, Microsoft.BizTalk.DefaultPipelines namespace
- Microsoft.BizTalk.DefaultPipelines namespace
ms.assetid: a54f8813-9c6f-4afe-8c76-2db3fa478947
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ad7cad78e3e8606371a5fa49673297cf590ddbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263412"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a>Referencia de Microsoft.BizTalk.DefaultPipelines
El **Microsoft.BizTalk.DefaultPipelines** espacio de nombres contiene las siguientes canalizaciones:  
  
-   XMLReceive  
  
-   PassThruReceive  
  
-   XMLTransmit  
  
-   PassThruTransmit  
  
 Una canalización es un componente de software que define y vincula una o varias fases para procesar los mensajes recibidos o enviados mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Las canalizaciones incluyen funciones, como la codificación o descodificación, el ensamblado o desensamblado, y el cifrado o descifrado. Estas funciones se implementan en un orden específico. La herramienta Diseñador de canalizaciones se utiliza para crear canalizaciones de recepción y de envío.  
  
 Las referencias predeterminadas de canalización incluidas en un proyecto de BizTalk pueden procesar todos los tipos de documentos mediante el **PassThruReceive** y **PassThruTransmit** canalizaciones.  
  
 En las listas siguientes se muestran los componentes predeterminados de las canalizaciones predeterminadas. En estas listas también se indica el orden predeterminado de los componentes de cada canalización. Si fuera necesario, puede agregar y eliminar componentes.  
  
 Los componentes predeterminados de la canalización XMLReceive predeterminada son:  
  
-   Descifrador  
  
-   Descodificador  
  
-   Desensamblador  
  
-   Validador  
  
-   Resolución de entidades  
  
 Los componentes predeterminados de la canalización XMLTransmit predeterminada son:  
  
-   Ensamblador  
  
-   Codificador  
  
-   Cifrador  
  
## <a name="see-also"></a>Vea también  
 [Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md)   
 [Referencias de Namespace de BizTalk incluidos en los proyectos de BizTalk](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)