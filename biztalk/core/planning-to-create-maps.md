---
title: Planeación de la creación de mapas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, planning
ms.assetid: e86af976-b989-4e24-80d5-3a9a3ac4e443
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb421f7ca67fce583fde7a7b85e653209da6d5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981853"
---
# <a name="planning-to-create-maps"></a>Planear la creación de asignaciones
Las asignaciones se utilizan para convertir mensajes de entrada que se ajustan a un esquema en mensajes de salida que se ajustan a un esquema diferente. Estas conversiones pueden ser simples o bastante complejas, conllevar cálculos y consolidación de información.  

 En la tabla siguiente se enumeran algunas de las preguntas que es preciso responder al planear la creación de asignaciones.  


|       Pregunta preliminar        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Recomendación                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ¿Qué asignaciones necesito crear? |                                                                                                                  Elabore una lista con los documentos empresariales que procesará con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Dicha lista puede incluir, por ejemplo, un pedido, una factura, una confirmación de envío, etc. La lista también puede incluir más de uno de esos documentos empresariales como, por ejemplo, cuando la estructura de un pedido que recibe de un socio comercial es diferente de la estructura del pedido que recibe de otro socio comercial.<br /><br /> Revise la lista y decida qué documentos necesitan estar en un formato diferente o qué documentos se controlan mejor al convertirlos a un formato común.                                                                                                                   |
|     ¿Dónde necesito asignaciones?      |                                                                                                                                                                                                                                                                                                                                                                                            Puede utilizar asignaciones en los puertos de envío, puertos de recepción y en las orquestaciones que representan procesos empresariales. Considere dónde desea o necesita convertir documentos.                                                                                                                                                                                                                                                                                                                                                                                            |
| ¿Tengo asignaciones antiguas que convertir? | Las asignaciones creadas en [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 se deben migrar sin modificación. Dedique el tiempo suficiente para probar las asignaciones migradas. Sin embargo, los mapas creados en versiones anteriores de BizTalk no pueden abrir necesariamente en BizTalk Server. **Nota:** asignaciones crean en las versiones anteriores a [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] pueden funcionar correctamente en [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009. Sin embargo, no pueden abrir los mapas en BizTalk Server. <br /><br /> Que contiene se asigna **Scripting** functoids personalizados o puede requerir un trabajo adicional. Para obtener más información, consulte [migrar Functoids](../core/migrating-functoids.md). |

## <a name="see-also"></a>Vea también  
 [Acerca de las asignaciones](../core/about-maps.md)   
 [Functoids de migración](../core/migrating-functoids.md)