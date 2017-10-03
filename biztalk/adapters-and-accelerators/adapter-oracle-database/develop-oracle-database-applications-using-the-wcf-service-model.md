---
title: Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performing operations, by using the WCF service model
- developing applications, by using the WCF service model
- WCF service model, using to develop applications
ms.assetid: 3f2c60b2-4835-492d-8c3c-ed35d3e4c517
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 548ca256d4395aefd67681229e9669ef2afcc2f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-oracle-database-applications-using-the-wcf-service-model"></a>Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF
En el nivel más bajo, el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] presenta un modelo de programación en el que los clientes invocar operaciones en un servicio mediante el intercambio de mensajes SOAP a través de un canal establecido entre los extremos de cliente y el servicio. Este modelo, conocido como el modelo de canal WCF expone los tipos de datos y métodos que permiten trabajar directamente en la arquitectura de canal WCF. El modelo de canal WCF proporciona control directo sobre el contenido de los mensajes SOAP que crea y sobre la forma tanto la aplicación y la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumirlos; sin embargo, crear mensajes SOAP con formato correcto para enviar a través de un canal y validar el mensajes de respuesta devueltos pueden ser una tarea detallada y exigente.  
  
 Por esta razón, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona otro modelo de programación que llama el modelo de servicio WCF. El modelo de servicio WCF implica el uso de las clases de proxy para invocar operaciones en un servicio de destino o para operaciones de recepción de un cliente.  
  
-   La clase de proxy que se utiliza para invocar operaciones en un servicio de destino se denomina una clase de cliente WCF. Esta clase modela las operaciones expuestas por un servicio como métodos de .NET con parámetros fuertemente tipados. Mediante el modelo de servicio WCF, puede invocar las operaciones expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] como métodos de .NET en el cliente de WCF. Para obtener más información acerca de los clientes WCF, vea "Información general de cliente de WCF" en [http://go.microsoft.com/fwlink/?LinkId=91458](http://go.microsoft.com/fwlink/?LinkId=91458).  
  
-   En el modelo de servicio WCF, el contrato de servicio expuesto por un servicio se representa mediante una interfaz. Esta representación de código administrado del contrato de servicio se llama a un contrato de servicio WCF. El contrato de servicio WCF modela las operaciones como métodos que tienen parámetros fuertemente tipados. Para una operación de recepción de un cliente se implementa una clase, el servicio WCF, desde esta interfaz. A continuación, puede hospedar una instancia de esta clase en un **System.ServiceModel.ServiceHost** para permitir que un cliente invocar la operación en el código. Al usar el modelo de servicio WCF y un contrato de servicio WCF de destino para la operación de POLLINGSTMT, puede recibir los resultados de una operación de sondeo en la base de datos de Oracle mediante [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 Usar herramientas para generar una clase de cliente WCF o un contrato de servicio WCF y código auxiliar de los metadatos del servicio asociado que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone. Puede utilizar cualquiera de las siguientes herramientas:  
  
-   El ServiceModel Metadata Utility Tool (svcutil.exe), que se suministra con WCF  
  
-   El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], que se incluye con el[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] se integra con la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] experiencia de diseño y presenta un estándar de Microsoft Windows de la interfaz que proporciona exploración y capacidades en las operaciones expuestas por el adaptador de búsqueda eficaces. Para obtener más información sobre cómo generar un cliente WCF o un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para artefactos de solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
 Dado que presenta un modelo que resulte familiar a los programadores de .NET y que oculta las complejidades subyacentes de intercambio de mensajes SOAP a través de un canal, el modelo de servicio WCF suele ser la mejor opción para desarrollar soluciones de programación para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Sin embargo, hay escenarios en que el modelo del canal WCF podría ser una opción mejor. Por ejemplo, el modelo de servicio WCF solo admite la transmisión por secuencias para la operación de ReadLOB. Esto se debe serializar y deserializar entre la representación XML de objetos en un mensaje SOAP y los tipos de .NET que se utilizan para representarlos en el modelo de servicio consiste en leer el mensaje completo en la memoria. (El resultado de una operación de ReadLOB es una excepción a esta regla).  
  
 El modelo de canal WCF proporciona compatibilidad para la transmisión por secuencias de nivel de nodo XML en todas las operaciones y el nivel de datos de transmisión por secuencias en las operaciones de ReadLOB y UpdateLOB. Si está trabajando con las consultas que devuelven conjuntos de resultados grandes o están intentando actualizar un campo LOB en una tabla, el modelo del canal WCF podría ser una opción mejor. Para obtener más información acerca de cómo utilizar el modelo de canal WCF, vea [desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).  
  
 Los temas de esta sección contienen información, procedimientos y ejemplos para ayudarle a crear y utilizar el modelo de servicio WCF para desarrollar aplicaciones mediante el uso de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de servicio WCF con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)  
  
-   [Metadatos y el modelo de servicio WCF con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/metadata-and-the-wcf-service-model-with-oracle-database.md)  
  
-   [Generar un cliente WCF o un contrato de servicio WCF para los artefactos de solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)  
  
-   [Configurar un enlace de cliente para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)  
  
-   [Realizar básicas Insert, Update, Delete y las operaciones Select mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)  
  
-   [Completar las operaciones en tablas con tipos de datos de gran tamaño de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)  
  
-   [Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [Llevar a cabo operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [Realizar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [Realizar una operación SQLEXECUTE en base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [Recibir mensajes de cambio de datos basado en sondeo de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)  
  
-   [Recibir notificaciones de cambio de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)