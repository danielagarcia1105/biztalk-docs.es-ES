---
title: Desarrollar aplicaciones de Oracle E-Business Suite en BizTalk | Microsoft Docs
description: Crear aplicaciones de Oracle EBS con WCF, o en el servidor BizTalk Server con el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7b1ebff-b3f8-4e07-a089-d1d5bfb78d56
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc00f1b22777829b314ccd1171cbc7fb6b4e5ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972821"
---
# <a name="develop-your-oracle-e-business-suite-applications"></a>Desarrollar aplicaciones de Oracle E-Business Suite

## <a name="overview"></a>Información general
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace. Las aplicaciones cliente pueden consumir el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para invocar operaciones en los artefactos de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pueden utilizarse:  
  
- A través de un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Mediante la invocación de métodos en una instancia de un proxy de cliente.  
  
- Mediante el envío de mensajes SOAP a través de una instancia de canal en el código que usa el modelo de canal WCF.  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>Canal WCF de BizTalk frente a WCF service frente a 
  
 En la tabla siguiente:  
  
- Enumera las distintas operaciones que se pueden realizar en Oracle E-Business Suite mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
- Proporciona vínculos a temas que contienen información acerca de cómo realizar la tarea mediante el enfoque elegido ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], modelo de canal de WCF o el modelo de servicio WCF).  
  
|Operación|BizTalk Server|Modelo de servicio WCF|Modelo del canal de WCF|  
|---|---|---|---|  
|Realizar operaciones en tablas y vistas | [Insertar, actualizar, eliminar o seleccionar en tablas y vistas de interfaz con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-or-select-on-interface-tables-and-views-with-oracle-ebs.md) |[Insertar, actualizar, eliminar o seleccionar las operaciones en tablas y vistas que usan el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)|  
|Realizar operaciones en tablas y vistas con tipos de datos de gran tamaño | [Completar operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md) |[Completar operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)||  
|Realizar operaciones compuestas en la base de datos de Oracle | [Completar operaciones compuestas en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/complete-composite-operations-on-oracle-e-business-suite.md)|||  
|Invocar programas simultáneos en Oracle E-Business Suite | [Invocar programas simultáneos en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-concurrent-programs-in-oracle-e-business-suite.md) | [Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Solicitud de invocación se establece en Oracle E-Business Suite | [Invocar conjuntos de solicitudes en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite.md) | [Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Realización de operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery| [Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-or-executenonquery-in-oracle-e-business-suite.md) |[Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)||  
|Base de datos de Oracle de sondeo mediante BizTalk Server|[Sondear Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)|[Sondear Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite|[Recibir notificaciones de cambio de base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)|[Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)|  

## <a name="next-steps"></a>Pasos siguientes  
 Los temas de esta sección proporcionan información de procedimientos y ejemplos que le ayudarán a desarrollar aplicaciones que consumen el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] tanto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y soluciones de programación. NET. 
  
-   [Crear una conexión a Oracle EBS](create-a-connection-to-oracle-e-business-suite.md)
-   [Obtener metadatos para operaciones de Oracle EBS en Visual Studio](get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)
-   [Trabajar con las propiedades de enlace](read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)
-   [Recibir mensajes de cambio de datos basados en sondeos](receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)
-   [Habilitar transacciones con MSDTC](enable-ms-dtc-to-allow-transactions-for-oracle-e-business-suite-adapter.md)
-   [Desarrollar aplicaciones de BizTalk con el adaptador de Oracle EBS](develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)
-   [Desarrollar aplicaciones con el modelo de servicio WCF](develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)
-   [Desarrollar aplicaciones con el modelo de canal WCF](develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)
-   [Usar el adaptador de Oracle EBS con SharePoint](use-the-oracle-e-business-suite-adapter-with-sharepoint.md)
-   [Ejemplos](samples-for-the-oracle-ebs-adapter.md)
-   [Configurar propiedades de transacción y el contexto de la aplicación](configure-transaction-properties-and-application-context-in-oracle-ebs-adapter.md)
  
