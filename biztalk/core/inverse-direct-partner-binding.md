---
title: Enlace de socio directo inverso | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, partners
- process management solution tutorial, partner binding
ms.assetid: 4cf8717a-2098-46f4-8f58-9d05fb562e2a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c9fe5e51f9f63ea098fa623dafbceeb670e75f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262396"
---
# <a name="inverse-direct-partner-binding"></a>Enlace de socio directo inverso
La solución Administración de procesos empresariales está diseñada para poder cambiar las fases de procesamiento de pedidos sin detener la aplicación. Para desacoplar las fases de procesamiento (**CableOrder1**, **CableOrder2**) desde el Administrador de procesos (**OrderManager**), la solución utiliza una técnica diferente para enlazar puertos entre estas orquestaciones.  
  
 En la forma habitual de enlace, enlace directo la **OrderManager** orquestación utilizaría la orquestación de la fase de proceso como el valor para la propiedad de puerto de orquestación de socio comercial. En el enlace directo así la **OrderManager** orquestación depende de los nombres seguros (que incluyen las versiones) de las fases de proceso. Esto hace imposible modificar las fases de proceso sin necesidad de volver a implementar el **OrderManager** orquestación. Para obtener más información sobre el enlace directo, vea [enlaces de puerto](../core/port-bindings.md). El enlace directo se puede ilustrar del siguiente modo:  
  
 ![Diagrama de enlace de socio directo inverso](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")  
  
 En el enlace de socio directo inverso, la orquestación receptora especifica el enlace, en lugar de la orquestación de origen. El puerto en el **OrderManager** simplemente está enlazado a sí mismo. Es decir, el puerto en el **OrderManager** se especifica para el **PartnerOrchestrationPort** propiedad. Sin embargo, utilizan la sintaxis de las orquestaciones de la fase de proceso **OrderManager** puerto como el valor de la **PartnerOrchestrationPort** propiedad. Esto desacopla el **OrderManager** a las versiones de las orquestaciones de la fase de proceso y permite cambiarlas sin volver a implementar el **OrderManager**. El enlace directo no permitiría este desacoplamiento. El enlace de socio directo inverso se puede ilustrar del siguiente modo:  
  
 ![Diagrama de enlace directo](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")  
  
> [!NOTE]
>  El enlace directo inverso permite también la comunicación con orquestaciones de socios de un modo similar a una lista de distribución. El **OrderManger** puede utilizar un puerto único para comunicarse con todas las fases. Esto permite agregar y quitar fases sin diseñar de nuevo la orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [Lógica del Administrador de procesos](../core/process-manager-logic.md)