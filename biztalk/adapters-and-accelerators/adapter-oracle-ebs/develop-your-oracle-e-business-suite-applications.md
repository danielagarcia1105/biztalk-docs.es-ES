---
title: Desarrollar las aplicaciones de Oracle E-Business Suite en BizTalk | Documentos de Microsoft
description: Crear aplicaciones de Oracle EBS mediante WCF, o en el servidor BizTalk Server con el módulo de adaptador de BizTalk (BAP)
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
ms.openlocfilehash: dc72e5adbef300115189119ba77821a08883999a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217268"
---
# <a name="develop-your-oracle-e-business-suite-applications"></a>Desarrollar las aplicaciones de Oracle E-Business Suite

## <a name="overview"></a>Información general
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace. Las aplicaciones cliente pueden utilizar la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para invocar operaciones en artefactos de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pueden utilizarse:  
  
-   A través de un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Mediante la invocación de métodos en una instancia de un proxy de cliente.  
  
-   Mediante el envío de mensajes SOAP a través de una instancia de canal en el código que usa el modelo de canal WCF.  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>Canal WCF de vs del servicio WCF de BizTalk vs 
  
 En la tabla siguiente:  
  
-   Enumera las distintas operaciones que pueden realizarse en Oracle E-Business Suite con la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
-   Proporciona vínculos a temas que contienen información acerca de cómo realizar la tarea mediante el método elegido ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], modelo de canales de WCF o el modelo de servicio WCF).  
  
|Operación|BizTalk Server|Modelo de servicio WCF|Modelo del canal de WCF|  
|---|---|---|---|  
|Realizar operaciones en tablas de interfaz y vistas | [Insertar, actualizar, eliminar o seleccionar en tablas de interfaz y las vistas de interfaz con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-or-select-on-interface-tables-and-views-with-oracle-ebs.md) |[Insertar, actualizar, eliminar o seleccionar operaciones en tablas de interfaz y vistas que usan el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)|  
|Realizar operaciones en tablas y vistas con tipos de datos de gran tamaño | [Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md) |[Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)||  
|Realizar operaciones compuestas en base de datos de Oracle | [Completar operaciones compuestas en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/complete-composite-operations-on-oracle-e-business-suite.md)|||  
|Invocar programas simultáneos en Oracle E-Business Suite | [Invocar programas simultáneos en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-concurrent-programs-in-oracle-e-business-suite.md) | [Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Solicitud de invocación se establece en Oracle E-Business Suite | [Invocar conjuntos de solicitudes en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite.md) | [Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Realizar operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery| [Operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-or-executenonquery-in-oracle-e-business-suite.md) |[Operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)||  
|Base de datos de Oracle de sondeo mediante BizTalk Server|[Sondeo Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)|[Sondeo Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite|[Recibir notificaciones de cambio de base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)|[Sondeo Oracle E-Business Suite con la instrucción SELECT con el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)|  

## <a name="next-steps"></a>Pasos siguientes  
 Los temas de esta sección proporcionan información, procedimientos y ejemplos que le ayudarán a desarrollar aplicaciones que consumen la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] tanto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y soluciones de programación. NET. 
  
-   [Crear una conexión a Oracle EBS](create-a-connection-to-oracle-e-business-suite.md)
-   [Obtiene los metadatos para operaciones de Oracle EBS en Visual Studio](get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)
-   [Trabajar con las propiedades de enlace](read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)
-   [Recibir mensajes de cambio de datos basado en sondeo](receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)
-   [Habilitar transacciones con MSDTC](enable-ms-dtc-to-allow-transactions-for-oracle-e-business-suite-adapter.md)
-   [Desarrollar aplicaciones de BizTalk con el adaptador de Oracle EBS](develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)
-   [Desarrollar aplicaciones mediante el modelo de servicio de WCF](develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)
-   [Desarrollar aplicaciones mediante el modelo de canal de WCF](develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)
-   [Utilizar el adaptador de Oracle EBS con SharePoint](use-the-oracle-e-business-suite-adapter-with-sharepoint.md)
-   [Ejemplos](samples-for-the-oracle-ebs-adapter.md)
-   [Configurar propiedades de transacción y el contexto de la aplicación](configure-transaction-properties-and-application-context-in-oracle-ebs-adapter.md)
  
