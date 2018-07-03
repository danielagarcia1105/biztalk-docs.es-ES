---
title: Mediante la transformación dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb83c4dc90a513367d2c914dc546eb0fd931d67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006139"
---
# <a name="using-dynamic-transformation"></a>Uso de la transformación dinámica
## <a name="overview"></a>Información general  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite tres mecanismos para la transformación dinámica:  
  
- Un agente de la transformación dinámica implementado como una orquestación  
  
- Un servicio Web de la transformación dinámica que incluye con el núcleo de servicios Web  
  
- Transformaciones que se ejecutan los componentes de canalización ESB  
  
  En esta sección se centra en el agente de transformación que se implementa como una orquestación. Para obtener información acerca de la transformación del servicio Web, consulte [mediante los servicios Web de BizTalk ESB Toolkit](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md). Para obtener información acerca de los componentes de canalización del distribuidor de ESB, consulte [mediante los componentes de soporte técnico de canalización](../esb-toolkit/using-the-pipeline-support-components.md).  
  
## <a name="how-it-works"></a>Funcionamiento  
 El agente de entrega de la transformación es una orquestación que se suscribe a mensajes donde la **nombre** atributo del elemento actual **ServiceInstance** es el elemento en el itinerario  **Microsoft.Practices.ESB.Services.Transform**. El agente realiza la siguiente secuencia de operaciones:  
  
1.  Recibe un mensaje sin tipo (System.Xml.XmlDocument).  
  
2.  Si el nombre de la asignación está disponible como un valor estático en el itinerario, el agente intenta resolver el nombre de la asignación mediante el Administrador de resolución.  
  
3.  Aplica la asignación adecuada para el mensaje de origen de entrada.  
  
4.  Publica la salida de mapa en la base de datos de cuadro de mensaje de BizTalk.  
  
## <a name="how-to-configure-dynamic-transformation"></a>Cómo configurar la transformación dinámica  
 Para obtener más información sobre cómo configurar la transformación dinámica con el Diseñador de itinerario, consulte [crear itinerarios usar diseñador de itinerario](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).  
  
## <a name="dynamic-transformation-errors"></a>Errores de transformación dinámica  
 El mecanismo de transformación dinámica creará y publicará un mensaje de error ESB en los casos siguientes:  
  
- El componente de resolución no puede determinar que se asignan a aplicar.  
  
- La asignación especificada no está disponible (por ejemplo, ha especificado un tipo de asignación incorrecta o un mapa no ha implementado todavía en BizTalk Server 2009).  
  
- Se produce un error durante la asignación (por ejemplo, el documento de origen no es del tipo de origen correctos o las referencias de mapa no se implementa una función personalizada en un ensamblado externo a BizTalk).  
  
- Se produce una excepción durante la resolución de just-in-time (JIT) del tipo de mapa.  
  
- No existe ningún suscriptor para el mensaje de salida.  
  
- Se produce cualquier excepción del sistema.  
  
  Es responsabilidad del desarrollador para proporcionar la información de contexto utilizada para rellenar los mensajes de excepción y crear controladores para reaccionar a la excepción. Está disponible automáticamente algunos de los datos y un controlador genérico recogerá el mensaje de excepción si no hay ningún controlador de destino está especificado o disponible. Para obtener más información sobre el control de excepciones de la transformación dinámica, consulte [usando administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).