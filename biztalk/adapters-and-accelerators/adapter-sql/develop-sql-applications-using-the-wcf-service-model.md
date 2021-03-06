---
title: Desarrollar aplicaciones de SQL con el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3ecfd6f-9144-4e41-a4b8-0c768a6ac254
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afeb8d7aac2dd2a29f60c89cf54c86ef2e4519df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983981"
---
# <a name="develop-sql-applications-using-the-wcf-service-model"></a>Desarrollar aplicaciones de SQL con el modelo de servicio de WCF
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] Proporciona un modelo de programación llamado el modelo de servicio WCF, como una alternativa al modelo de programación de canal WCF.  
  
 El modelo de servicio WCF usa los paradigmas familiares de .NET para ocultar las complejidades de intercambio de mensajes SOAP a través de un canal. El modelo de servicio lleva a cabo esta simplificación, lea todo el mensaje SOAP en la memoria antes de copiar la información en estructuras de datos. NET. Cargando mensajes largos en la memoria, sin embargo, puede no resultar práctico en algunas aplicaciones. En estos casos, los desarrolladores deben usar el modelo de canal WCF. Para obtener más información acerca de cómo utilizar el modelo de canal WCF, vea [aplicaciones de desarrollo de SQL mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).  
  
 En el nivel más bajo, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] presenta el modelo de canal WCF, en el que los clientes invocar operaciones en un servicio mediante el intercambio de mensajes SOAP a través de un canal establecido entre los puntos de conexión de cliente y servicio. El modelo del canal WCF expone los tipos de datos y métodos que permiten trabajar directamente en la arquitectura de canal WCF. El modelo del canal WCF le brinda un control directo sobre el contenido de los mensajes SOAP que crea y sobre la forma tanto la aplicación y el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] consumirlos. Sin embargo, crear mensajes SOAP tiene el formato correcto para enviar a través de un canal y validar los mensajes de respuesta devueltos pueden ser una tarea exigente y detallada.  
  
 El modelo de servicio WCF usa las clases de proxy para invocar operaciones en un servicio de destino o para operaciones de recepción de un cliente. La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la base de datos de SQL Server como un servicio WCF en el que puede invocar las operaciones.  
  
- La clase de proxy que se utiliza para invocar operaciones en un servicio de destino se llama a una clase de cliente WCF. Esta clase modela las operaciones expuestas por un servicio como métodos de .NET con parámetros fuertemente tipados. Mediante el modelo de servicio WCF, puede invocar las operaciones expuestas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] como métodos de .NET en el cliente de WCF. Para obtener más información acerca de los clientes de WCF, vea [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx).
  
  Puede utilizar cualquiera de las siguientes herramientas para generar una clase de cliente WCF y código auxiliar de los metadatos del servicio asociado que la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone:  
  
- **ServiceModel Metadata Utility Tool (svcutil.exe)**, que se suministra con WCF.  
  
- **El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** , que se suministra con [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y se integra con la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] experiencia de diseño. Esta herramienta presenta una interfaz estándar de Microsoft Windows que proporciona eficaces de exploración y búsqueda capacidades en las operaciones que expone el adaptador. Para obtener más información sobre cómo generar una aplicación de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
   Los temas de esta sección contienen información, procedimientos y ejemplos que le ayudarán a crear y usar el modelo de servicio WCF para desarrollar aplicaciones mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de servicio WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [Los metadatos y el modelo de servicio WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/metadata-and-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [Generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)  
  
-   [Configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)  
  
-   [Insertar, actualizar, eliminar o seleccionar las operaciones en tablas y vistas que usan el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [Ejecutar operaciones en tablas y vistas con tipos de datos grandes en SQL mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)  
  
-   [Invocar procedimientos almacenados en SQL mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [Invocar funciones escalares en SQL Server mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [Invocar funciones con valores de tabla en SQL Server mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery en SQL mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)  
  
-   [Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)  
  
-   [Recibir notificaciones de consulta de SQL mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-from-sql-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)