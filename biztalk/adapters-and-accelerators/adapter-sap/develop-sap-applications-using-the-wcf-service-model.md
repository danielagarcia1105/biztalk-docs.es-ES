---
title: Desarrollar aplicaciones de SAP mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, developing applications
ms.assetid: 5387d063-31d3-49b3-9771-354802542f8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e47e652f01f29c33952187f165c428df63a45c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998653"
---
# <a name="develop-sap-applications-using-the-wcf-service-model"></a>Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF
En el nivel más bajo, el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] presenta un modelo de programación en el que los clientes invocar operaciones en un servicio mediante el intercambio de mensajes SOAP a través de un canal establecido entre los puntos de conexión de cliente y servicio. Este modelo, conocido como el modelo de canal WCF expone los tipos de datos y métodos que permiten trabajar directamente en la arquitectura de canal WCF. El modelo del canal WCF le brinda un control directo sobre el contenido de los mensajes SOAP que crea y sobre la forma tanto la aplicación y el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] consumirlos; sin embargo, crear mensajes SOAP tiene el formato correcto para enviar a través de un canal y validar el los mensajes de respuesta devueltos pueden ser una tarea exigente y detallada.  
  
 Por este motivo, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona otro modelo de programación llamado el modelo de servicio WCF. El modelo de servicio WCF implica el uso de clases de proxy para invocar operaciones en un servicio de destino o para operaciones de recepción de un cliente.  
  
- La clase de proxy que se utiliza para invocar operaciones en un servicio de destino se llama a una clase de cliente WCF. Esta clase modela las operaciones expuestas por un servicio como métodos de .NET con parámetros fuertemente tipados. Mediante el modelo de servicio WCF, puede invocar las operaciones expuestas por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como métodos de .NET en el cliente de WCF. Para obtener más información acerca de los clientes de WCF, vea [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx).
  
- La clase de proxy usada para una operación de recepción desde un cliente se denomina una clase de contrato de servicio WCF. Esta clase modela una operación expuesta por el código como un método de devolución de llamada con parámetros fuertemente tipados. A continuación, puede hospedar una instancia de esta clase en un **System.ServiceModel.ServiceHost** para permitir que un cliente invocar la operación en el código. Mediante el modelo de servicio WCF y una clase de contrato de servicio WCF de destino para la operación POLLINGSTMT, puede recibir los resultados de una consulta de sondeo desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
  Usar herramientas para generar una clase de cliente WCF o un contrato de servicio WCF y código auxiliar de los metadatos del servicio asociado que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone. Puede usar cualquiera de las siguientes herramientas:  
  
- El ServiceModel Metadata Utility Tool (svcutil.exe), que se suministra con WCF  
  
- El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], que se incluye con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]  
  
  El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] se integra con la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] experiencia de diseño y presenta un Windows Microsoft estándar de la interfaz que proporciona eficaces examinar y buscar en las capacidades en las operaciones expuestas por el adaptador. Para obtener más información sobre cómo generar un cliente de WCF o una clase de contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de solución de SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
  Dado que presenta un modelo que resultará familiar a los programadores de .NET y que oculta la complejidad subyacente del intercambio de mensajes SOAP a través de un canal, el modelo de servicio WCF suele ser la mejor opción para desarrollar soluciones de programación para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Sin embargo, hay escenarios en que el modelo del canal WCF podría ser una mejor elección; es importante especialmente en escenarios en la transmisión por secuencias. Esto se debe serializar y deserializar entre la representación XML de objetos en un mensaje SOAP y los tipos de .NET que se utilizan para representarlos en el modelo de servicio consiste en leer el mensaje completo en la memoria. Para obtener más información acerca de cómo utilizar el modelo de canal WCF, vea [aplicaciones de desarrollo de SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).
  
  Los temas de esta sección contienen información, procedimientos y ejemplos que le ayudarán a crear y usar el modelo de servicio WCF para desarrollar aplicaciones mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de servicio WCF con el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)  
  
-   [Los metadatos y el modelo de servicio WCF con SAP](../../adapters-and-accelerators/adapter-sap/metadata-and-the-wcf-service-model-with-sap.md)  
  
-   [Generar un cliente de WCF o un contrato de servicio WCF para artefactos de solución de SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)  
  
-   [Configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)  
  
-   [Invocar RFC de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [Recibir llamadas RFC de entrada de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [Invocar trfc mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [Recibir llamadas de tRFC de entrada de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [Invocar BAPI de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)  
  
-   [Enviar los IDOC a SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)