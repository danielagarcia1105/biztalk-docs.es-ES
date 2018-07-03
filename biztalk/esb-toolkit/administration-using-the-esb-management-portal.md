---
title: Administración mediante el Portal de administración de ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 478d1dcc-e9b2-443b-be98-5b7545322401
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c44951b4284e0d17b2d8e69011cedfa213c219
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967765"
---
# <a name="administration-using-the-esb-management-portal"></a>Administración mediante el Portal de administración de ESB
El Portal de administración de ESB, incluido como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], es un sitio de ejemplo que muestra el uso de las métricas y las posibilidades que existen para extender el Kit de herramientas de ESB de BizTalk. El portal proporciona un punto de partida desde el que puede crear su propio portal personalizado.  
  
 El Portal de administración de ESB también es una herramienta de alta capacidad y útil que puede ayudar a maximizar el uso y la eficacia del sistema de administración de excepciones de ESB. Además, el portal proporciona una interfaz de usuario para un servidor de registro Universal Description, Discovery and Integration (UDDI) subyacente y capacidades de configuración gráfica para características como la auditoría, ver información del historial, configurar las alertas y notificaciones y permitir que los usuarios para suscribirse a alertas que indican errores que se produzcan en las aplicaciones de ESB.  
  
 En esta sección se describe las tareas comunes que puede realizar mediante el Portal de administración de ESB, incluidas las siguientes:  
  
-   [Trabajar con excepciones y mensajes de error](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [Configuración de alertas, notificaciones y suscripciones](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [Ver y administrar auditoría e historial](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [Análisis de las tendencias de errores mediante gráficos e informes](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [Ver y publicar registros de UDDI](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  Para obtener una descripción detallada de las características del Portal de administración de ESB individuales, consulte [referencia de características de Portal de administración de ESB](../esb-toolkit/esb-management-portal-feature-reference.md).  
  
## <a name="esb-portal-technologies"></a>Tecnologías de Portal de ESB  
 El Portal de administración de ESB aprovecha las ventajas de las siguientes tecnologías:  
  
- [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
- ASP.NET
  
- [Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)). El Portal de administración de ESB usa los siguientes ensamblados de Enterprise Library:  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Caching**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Common**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Data**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Logging**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Validation**  
  
  -   Microsoft.Practices.Unity  
  
- [Microsoft Chart control](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) para Microsoft .NET Framework 4  
  
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía el seguimiento de la métrica solo para el seguimiento de errores para el sistema de administración de la excepción.