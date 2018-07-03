---
title: Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cf3430d-12e9-437c-b398-d978faa4da2b
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b290ef99349d970179b07ecfce45c72499d88c5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996021"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-service-model"></a>Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] Proporciona un modelo de programación llamado el modelo de servicio WCF para conectarse a la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]. Se agregó el modelo de servicio WCF para abordar, en parte, algunas de las limitaciones del modelo de programación de canal WCF.  
  
 El modelo de servicio WCF usa los paradigmas familiares de .NET para ocultar las complejidades de intercambio de mensajes SOAP a través de un canal. El modelo de servicio lleva a cabo esta simplificación, lea todo el mensaje SOAP en la memoria antes de copiar la información en estructuras de datos. NET. Cargando mensajes largos en la memoria puede no resultar práctico en algunas aplicaciones. En estos casos, los desarrolladores deben usar el modelo de canal WCF. Para obtener más información acerca de cómo utilizar el modelo de canal WCF, vea [desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md).  
  
 En el nivel más bajo, el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] presenta el modelo de canal WCF en el que los clientes invocar operaciones en un servicio mediante el intercambio de mensajes SOAP a través de un canal establecido entre los puntos de conexión de cliente y servicio. El modelo del canal WCF expone los tipos de datos y métodos que permiten trabajar directamente en la arquitectura de canal WCF. El modelo del canal WCF le brinda un control directo sobre el contenido de los mensajes SOAP que crea y sobre la forma tanto la aplicación y el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consumirlos. Sin embargo, crear mensajes SOAP tiene el formato correcto para enviar a través de un canal y validar los mensajes de respuesta devueltos pueden ser una tarea exigente y detallada.  
  
 El modelo de servicio WCF usa las clases de proxy para invocar operaciones en un servicio de destino o para operaciones de recepción de un cliente. La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone Oracle E-Business Suite como un servicio WCF en el que puede invocar las operaciones.  
  
- La clase de proxy que se utiliza para invocar operaciones en un servicio de destino se llama a una clase de cliente WCF. Esta clase modela las operaciones expuestas por un servicio como métodos de .NET con parámetros fuertemente tipados. Mediante el modelo de servicio WCF, puede invocar las operaciones expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] como métodos de .NET en el cliente de WCF. Para obtener más información acerca de los clientes de WCF, vea [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx).
  
  Puede utilizar cualquiera de las siguientes herramientas para generar una clase de cliente WCF y código auxiliar de los metadatos del servicio asociado que la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone:  
  
- **ServiceModel Metadata Utility Tool (svcutil.exe)**, que se suministra con WCF.  
  
- **El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** , que se incluye con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y se integra con la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] experiencia de diseño. Esta herramienta presenta una interfaz estándar de Microsoft Windows que proporciona eficaces de exploración y búsqueda capacidades en las operaciones que expone el adaptador. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
## <a name="in-this-section"></a>En esta sección  
 Los temas siguientes ofrecen información sobre cómo desarrollar aplicaciones que usan el modelo de servicio WCF:  
  
-   [Información general sobre el modelo de servicio WCF con el adaptador para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [Los metadatos y el modelo de servicio WCF con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/metadata-and-the-wcf-service-model-with-oracle-e-business-suite.md)  
  
-   [Generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)  
  
-   [Configurar un enlace de cliente de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)  
  
-   [Realización de Insert, Update, Delete o Select operaciones en tablas y vistas que usan el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)  
  
-   [Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [Realizar ExecuteReader, ExecuteScalar o ExecuteNonQuery operaciones en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)  
  
-   [Sondear Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [Recibir notificaciones de cambio de base de datos Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)