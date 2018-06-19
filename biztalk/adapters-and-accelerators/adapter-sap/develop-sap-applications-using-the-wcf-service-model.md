---
title: Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
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
ms.openlocfilehash: 4933610f8416b2c7fb81861562480e355dd8d373
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217180"
---
# <a name="develop-sap-applications-using-the-wcf-service-model"></a>Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF
En el nivel más bajo, el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] presenta un modelo de programación en el que los clientes invocar operaciones en un servicio mediante el intercambio de mensajes SOAP a través de un canal establecido entre los extremos de cliente y el servicio. Este modelo, conocido como el modelo de canal WCF expone los tipos de datos y métodos que permiten trabajar directamente en la arquitectura de canal WCF. El modelo de canal WCF proporciona control directo sobre el contenido de los mensajes SOAP que crea y sobre la forma tanto la aplicación y la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] consumirlos; sin embargo, crear mensajes SOAP con formato correcto para enviar a través de un canal y validar el mensajes de respuesta devueltos pueden ser una tarea detallada y exigente.  
  
 Por esta razón, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona otro modelo de programación que llama el modelo de servicio WCF. El modelo de servicio WCF implica el uso de las clases de proxy para invocar operaciones en un servicio de destino o para operaciones de recepción de un cliente.  
  
-   La clase de proxy que se utiliza para invocar operaciones en un servicio de destino se denomina una clase de cliente WCF. Esta clase modela las operaciones expuestas por un servicio como métodos de .NET con parámetros fuertemente tipados. Mediante el modelo de servicio WCF, puede invocar las operaciones expuestas por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como métodos de .NET en el cliente de WCF. Para obtener más información acerca de los clientes WCF, vea [información general sobre el cliente de WCF](https://msdn.microsoft.com/library/ms735103.aspx).
  
-   La clase de proxy usada para una operación de recepción de un cliente se llama una clase de contrato de servicio WCF. Esta clase modela una operación expuesta por el código como un método de devolución de llamada con parámetros fuertemente tipados. A continuación, puede hospedar una instancia de esta clase en un **System.ServiceModel.ServiceHost** para permitir que un cliente invocar la operación en el código. Al usar el modelo de servicio WCF y una clase de contrato de servicio WCF de destino para la operación de POLLINGSTMT, puede recibir los resultados de una consulta de sondeo de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
 Usar herramientas para generar una clase de cliente WCF o un contrato de servicio WCF y código auxiliar de los metadatos del servicio asociado que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone. Puede utilizar cualquiera de las siguientes herramientas:  
  
-   El ServiceModel Metadata Utility Tool (svcutil.exe), que se suministra con WCF  
  
-   El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], que se incluye con el[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] se integra con la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] experiencia de diseño y presenta un estándar de Microsoft Windows de la interfaz que proporciona exploración y capacidades en las operaciones expuestas por el adaptador de búsqueda eficaces. Para obtener más información sobre cómo generar un cliente WCF o una clase de contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para la solución SAP artefactos](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
 Dado que presenta un modelo que resulte familiar a los programadores de .NET y que oculta las complejidades subyacentes de intercambio de mensajes SOAP a través de un canal, el modelo de servicio WCF suele ser la mejor opción para desarrollar soluciones de programación para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Sin embargo, hay escenarios en que el modelo del canal WCF podría ser una opción mejor; especialmente en escenarios en que transmisión por secuencias es importante. Esto se debe serializar y deserializar entre la representación XML de objetos en un mensaje SOAP y los tipos de .NET que se utilizan para representarlos en el modelo de servicio consiste en leer el mensaje completo en la memoria. Para obtener más información acerca de cómo utilizar el modelo de canal WCF, vea [aplicaciones SAP desarrollar mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).
  
 Los temas de esta sección contienen información, procedimientos y ejemplos para ayudarle a crear y utilizar el modelo de servicio WCF para desarrollar aplicaciones mediante el uso de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de servicio WCF con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)  
  
-   [Metadatos y el modelo de servicio WCF con SAP](../../adapters-and-accelerators/adapter-sap/metadata-and-the-wcf-service-model-with-sap.md)  
  
-   [Generar un cliente de WCF o un contrato de servicio de WCF para la solución SAP artefactos](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)  
  
-   [Configurar un enlace de cliente para el sistema SAP.](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)  
  
-   [Invocar RFC en SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [Recibir las llamadas entrantes de RFC en SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [Invocar tRFCs mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [Recibir llamadas de tRFC entrante en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [Invocar BAPI en SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)  
  
-   [Enviar IDOC a SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)