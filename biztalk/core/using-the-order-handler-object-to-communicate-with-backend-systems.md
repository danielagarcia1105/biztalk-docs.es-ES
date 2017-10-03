---
title: Utilizando el objeto Orderhandler para comunicarse con sistemas de back-end | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d7621c4e5737def0e9fc0682de709ae57f98790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a>Utilizando el objeto Orderhandler para comunicarse con sistemas de back-end
La solución Administración de procesos empresariales puede comunicarse de distintas formas con el sistema de servidor de pedidos heredado, el sistema de suministro de cable que recibe los pedidos finales. La solución usa los recursos remotos de .NET que se encuentran en Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] para comunicarse con el sistema de suministro.  
  
 La solución usa una técnica habitual: utilizar una interfaz para definir el objeto de acceso al sistema de servidor. Al colocar la interfaz en un ensamblado independiente, el ensamblado de cliente puede tener acceso al objeto remoto sin tener que obtener acceso al ensamblado compilado.  
  
 El **IOrderHandler** interfaz define los métodos para comunicarse con el sistema de pedidos de back-end. Esta interfaz incluye métodos para analizar, activar, cancelar y realizar pedidos. También proporciona un método para identificar el tipo de servicio, un método necesario cuando se cancela un pedido.  
  
 El **CableOrder1**, **CableOrder2**, y las orquestaciones satélite utilizan el **OrderHandlerWrapper** objeto que implementa **IOrderHandler**. El **OrderHandlerWrapper** objeto, a su vez, invoca una instancia remota de un **OrderHandler** objeto proporcionado por el **CableProvisioningSystemServer** ejecutable. El uso del objeto contenedor satisface el requisito empresarial de utilizar funciones remotas .NET para la comunicación con el sistema de servidor de pedidos y, al mismo tiempo, permite usar las características de reintento de los componentes de control de excepciones.  
  
 Dado que uno debe ser capaz de serializar los objetos al que hace referencia en una orquestación, el **OrderHandlerWrapper** también se puede serializar. Mediante el **OrderHandlerWrapper** aísla el código de serialización de las orquestaciones.  
  
 Si examina el código, verá que el **OrderHandlerWrapper** objeto implementa explícitamente la **ISerializable** interfaz. El objeto debe controlar su propia serialización porque utiliza un constructor no predeterminado.  
  
 La utilización de características remotas .NET para la comunicación con el sistema de servidor es más eficaz que la mensajería. Además, en comparación con una solución pura de mensajería, permite enlazar de una forma más eficaz las orquestaciones con el sistema de servidor. Las características remotas .NET impiden asimismo que la solución aproveche las ventajas de las características integradas de peticiones de reintento de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [Lógica del Administrador de procesos](../core/process-manager-logic.md)