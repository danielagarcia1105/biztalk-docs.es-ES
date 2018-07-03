---
title: Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64cd124a-5e7f-4ee8-85d3-f9540b25d766
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ad676d737fffc45898c31f68d0895fc6919b63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984053"
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a>Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite
## <a name="overview"></a>Información general
Los clientes del adaptador pueden realizar operaciones en Oracle E-Business Suite por:  
  
- Crear proyectos de BizTalk  
  
- Mediante el modelo de canal WCF  
  
- Mediante el modelo de servicio WCF  
  
  La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones. Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal. Si se requiere una respuesta, se devuelve en un mensaje SOAP a través del canal mismo. Para obtener información acerca de la estructura del mensaje y la acción de SOAP asociada con cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).  
  
  Esta sección proporciona información acerca de las operaciones admitidas en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Establecer el contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [Operaciones en tablas y vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [Operaciones en las API de PL/SQL](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [Operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [Operaciones en conjuntos de solicitud](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [Operaciones en tablas y vistas de interfaz, tablas y vistas que contienen datos de LOB](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [Operaciones en tablas que contienen tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [Operaciones en funciones y procedimientos almacenados](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [Operaciones en funciones y procedimientos con parámetros de REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [Operaciones en funciones y procedimientos con tipos RECORD](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [Operaciones en sinónimos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [Consideración para recibir notificaciones de cambio de base de datos](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [Compatibilidad para las llamadas entrantes mediante sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [Compatibilidad para las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [Compatibilidad con las operaciones compuestas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [Compatibilidad con tipos definidos por el usuario de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a>Vea también  
[El adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)