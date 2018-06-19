---
title: Usar el enrutamiento dinámico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa3a35f-cafa-4524-8b96-f8a333b7ff87
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b668f53ba87a461441b0dbb498ae0677fa5956
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295700"
---
# <a name="using-dynamic-routing"></a>Usar el enrutamiento dinámico
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite enrutamiento dinámico de mensajes mediante un proceso integrado y un agente de entrega genérico; también admite enrutamiento dinámico de mensajes en la capa de mensajería con los componentes de canalización ESB distribuidor o distribuidor de ESB desensamblar.  
  
## <a name="overview"></a>Información general  
 El mecanismo de resolución dinámica de [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] habilita la detección de puntos de conexión cuando llega un mensaje o inmediatamente antes de que se entrega un mensaje.  
  
## <a name="how-it-works"></a>Funcionamiento  
 El agente de entrega genérico proporcionado con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] es un ejemplo y una guía para el desarrollo y el uso de técnicas de enrutamientos dinámicas. Puede crear a agentes de entrega adicionales o implementar a agentes de entrega que consta de un puerto de envío (que no implementan una orquestación) fácilmente. De forma predeterminada, los componentes de canalización de envío de ESB y desensamblador de envío de ESB ofrecen mucho más con optimización para la capacidad de enrutamiento dinámica.  
  
 El agente de entrega genérico implementa una orquestación que se suscribe a mensajes donde la **nombre** atributo del elemento actual **ServiceInstance** elemento en el itinerario es  **Microsoft.Practices.ESB.Services.Routing**. El agente realiza la siguiente secuencia de operaciones:  
  
1.  Recibe un mensaje sin tipo (System.Xml.XmlDocument).  
  
2.  Intenta resolver n número de puntos de conexión mediante el Administrador de resolución.  
  
3.  Usa el Administrador de adaptador para establecer las propiedades de punto de conexión de contexto del mensaje y el puerto dinámico lógico.  
  
4.  Publica el mensaje a través del puerto de envío de enlace directo, lo que desencadena la suscripción de servidor BizTalk Server en el puerto de envío dinámico para enrutar los mensajes adicionales.  
  
## <a name="how-to-configure-dynamic-routing"></a>Cómo configurar el enrutamiento dinámico  
 Para obtener más información acerca de cómo configurar el enrutamiento dinámico mediante el Diseñador de itinerario, vea Crear itinerarios uso itinerario del diseñador.  
  
## <a name="dynamic-routing-errors"></a>Errores de enrutamiento dinámicos  
 El mecanismo de enrutamiento dinámico se crear y publicar un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] mensaje de error en los siguientes casos:  
  
-   El agente de entrega no puede determinar el punto de conexión durante la resolución de just-in-time (JIT).  
  
-   Se produce un error de entrega.  
  
-   No existe ningún suscriptor para el mensaje de salida.  
  
-   Se produce cualquier excepción del sistema.