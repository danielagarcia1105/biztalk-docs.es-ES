---
title: Administración mediante el Portal de administración de ESB | Documentos de Microsoft
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
ms.openlocfilehash: 351d06df4d6384607564778c4b86d8c509379488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290276"
---
# <a name="administration-using-the-esb-management-portal"></a>Administración mediante el Portal de administración de ESB
El Portal de administración de ESB, incluido como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], es un sitio de ejemplo que muestra el uso de las métricas y las posibilidades que existen para extender el Kit de herramientas de ESB de BizTalk. El portal proporciona un punto de partida desde el que puede crear su propio portal personalizado.  
  
 El Portal de administración de ESB también es una herramienta de alta capacidad y útil que puede ayudar a maximizar el uso y la eficacia del sistema de administración de la excepción de ESB. Además, el portal proporciona una interfaz de usuario para un servidor de registro subyacente de Universal Description, Discovery y Integration (UDDI) y capacidades de configuración gráfica para características como la auditoría, ver la información de historial, configurar alertas y notificaciones y permitir a los usuarios para suscribirse a alertas que indican errores que se produzcan en las aplicaciones de ESB.  
  
 En esta sección se describe las tareas comunes que puede realizar con el Portal de administración de ESB, incluidas las siguientes:  
  
-   [Trabajar con excepciones y mensajes de error](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [Configuración de alertas, notificaciones y suscripciones](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [Ver y administrar auditoría e historial](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [Analizar las tendencias de errores mediante gráficos e informes](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [Ver y publicar los registros UDDI](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  Para obtener una descripción detallada de las características individuales del Portal de administración de ESB, consulte [referencia de características de Portal de administración de ESB](../esb-toolkit/esb-management-portal-feature-reference.md).  
  
## <a name="esb-portal-technologies"></a>Tecnologías de Portal de ESB  
 El Portal de administración de ESB aprovecha las ventajas de las siguientes tecnologías:  
  
-   [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
-   ASP.NET
  
-   [Biblioteca de información empresarial](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)). El Portal de administración de ESB usa los siguientes ensamblados de Enterprise Library:  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Caching**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Common**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Data**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Logging**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Validation**  
  
    -   Microsoft.Practices.Unity  
  
-   [Controles de gráfico de Microsoft](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) para Microsoft .NET Framework 4  
  
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] métrica seguimiento sólo se aplica a seguimiento de errores para el sistema de administración de la excepción.