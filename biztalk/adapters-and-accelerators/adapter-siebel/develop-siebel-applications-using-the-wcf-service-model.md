---
title: Desarrollar aplicaciones de Siebel mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, developing applications by using
- WCF service model, performing operations
- proxy programming, performing operations
- WCF service model, advantages of using
ms.assetid: df5627b9-c80d-4a75-a20a-a0be119735a2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492d3ca3dc132704913e54045f4c377a32903a67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984069"
---
# <a name="develop-siebel-applications-using-the-wcf-service-model"></a>Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF
[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Proporciona un modelo de programación denominada el modelo de servicio WCF, que, en parte, ayuda a abordar algunas de las limitaciones de otro modelo de programación, el modelo de canal WCF.  
  
 En el nivel más bajo, el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] presenta el modelo de canal WCF en el que los clientes invocar operaciones en un servicio mediante el intercambio de mensajes SOAP a través de un canal establecido entre los puntos de conexión de cliente y servicio. El modelo del canal WCF expone los tipos de datos y métodos que permiten trabajar directamente en la arquitectura de canal WCF. El modelo del canal WCF le brinda un control directo sobre el contenido de los mensajes SOAP que crea y sobre la forma tanto la aplicación y el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] consumirlos. Sin embargo, crear mensajes SOAP tiene el formato correcto para enviar a través de un canal y validar los mensajes de respuesta devueltos pueden ser una tarea exigente y detallada.  
  
 El modelo de servicio WCF, sin embargo, implica el uso de clases de proxy para invocar operaciones en un servicio de destino o para operaciones de recepción de un cliente. La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone el sistema Siebel como un servicio WCF en el que puede invocar las operaciones.  
  
- La clase de proxy que se utiliza para invocar operaciones en un servicio de destino se llama a una clase de cliente WCF. Esta clase modela las operaciones expuestas por un servicio como métodos de .NET con parámetros fuertemente tipados. Mediante el modelo de servicio WCF, puede invocar las operaciones expuestas por la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] como métodos de .NET en el cliente de WCF. Para obtener más información acerca de los clientes de WCF, vea [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx).   
  
  Usar herramientas para generar una clase de cliente WCF y código auxiliar de los metadatos del servicio asociado que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone. Puede usar cualquiera de las siguientes herramientas:  
  
- El ServiceModel Metadata Utility Tool (svcutil.exe), que se suministra con WCF  
  
- El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], que se incluye con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]  
  
  El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] se integra con la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] experiencia de diseño y presenta un Windows Microsoft estándar de la interfaz que proporciona eficaces examinar y buscar en las capacidades en las operaciones expuestas por el adaptador. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="why-choose-the-wcf-service-model-or-the-wcf-channel-model"></a>¿Por qué elegir el modelo de servicio WCF o el modelo del canal de WCF?  
 Dado que presenta un modelo que resultará familiar a los programadores de .NET y oculta la complejidad subyacente del intercambio de mensajes SOAP a través de un canal, el modelo de servicio WCF suele ser la mejor opción para desarrollar soluciones de programación para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Sin embargo, hay escenarios en que el modelo del canal WCF podría ser una opción mejor. Por ejemplo, serializar y deserializar entre la representación XML de objetos en un mensaje SOAP y los tipos de .NET que se utilizan para representarlos en el modelo de servicio WCF consiste en leer el mensaje completo en la memoria.  
  
 El modelo de canal WCF proporciona compatibilidad con streaming de nivel de nodo XML en todas las operaciones. En el nivel de nodo de streaming, solo en cada nodo del mensaje XML se mantiene en memoria en cualquier momento. Para determinadas operaciones, por ejemplo, si va a realizar consultas que devuelven conjuntos de resultados grandes, el modelo del canal WCF podría ser una opción mejor para su aplicación. Para obtener más información acerca de cómo utilizar el modelo de canal WCF, vea [desarrollar aplicaciones de Siebel mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md).  
  
 Los temas de esta sección contienen información, procedimientos y ejemplos que le ayudarán a crear y usar el modelo de servicio WCF para desarrollar aplicaciones mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de servicio WCF con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)  
  
-   [Los metadatos y el modelo de servicio WCF con Siebel](../../adapters-and-accelerators/adapter-siebel/metadata-and-the-wcf-service-model-with-siebel.md)  
  
-   [Generar un cliente de WCF o un contrato de servicio WCF para artefactos de solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
-   [Configurar un cliente de WCF para un sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)  
  
-   [Ejecutar operaciones en componentes empresariales con el adaptador de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)  
  
-   [Ejecutar operaciones en componentes empresariales con campos MVG con el adaptador de Siebel mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)  
  
-   [Invocar métodos de servicio empresarial con el adaptador de Siebel mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)