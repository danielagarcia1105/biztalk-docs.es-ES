---
title: Portal de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- activities [BAM], searching
- BAM portal
- BAM portal, features
- aggregations [BAM], BAM portal
- BAM portal, activity searches
- alerts, Alert Manager
- BAM portal, about BAM portal
- BAM, portals
- BAM portal, aggregations
ms.assetid: 593c9637-6b97-4ad8-8af7-2b49325acf10
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f86aad2a183653f00f1f7fc2533ac6956b2a85f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-portal"></a>Portal de BAM
Los usuarios empresariales finales utilizan el portal de BAM para supervisar los indicadores clave de rendimiento (KPI), que miden el progreso hacia un objetivo empresarial, y otra información acerca de sus procesos empresariales. Los analistas de negocios utilizan el portal de BAM para controlar la creación de modelos de observación, que son las definiciones de alto nivel de los requisitos de visibilidad dentro del proceso empresarial. Los administradores lo utilizan en un gran número de actividades de supervisión, que incluyen supervisar el estado del sistema de administración del proceso empresarial.  
  
## <a name="what-is-the-bam-portal"></a>¿Qué es el portal de BAM?  
 El portal de BAM proporciona visibilidad en tiempo real, de extremo a extremo a un proceso empresarial. Es una característica basada en Web que consta de una colección de páginas de ASP.NET. Puede personalizar BAM para mejorar el rendimiento y la experiencia de los usuarios.  
  
## <a name="why-use-the-bam-portal"></a>¿Por qué se utiliza el portal de BAM?  
 el portal de BAM permite efectuar búsquedas, agregar datos y establecer alertas en una vista de BAM, que constituye una perspectiva de los datos económicos. Esta visibilidad puede proporcionar la información necesaria de KPI para su empresa, o se puede utilizar como prueba de concepto antes de implementar otra solución, como extender una hoja de cálculo de Microsoft Office Excel, utilizar el informe de SQL o generar una interfaz de usuario personalizada.  
  
## <a name="bam-portal-components"></a>Componentes del portal de BAM  
 A continuación se muestra una breve descripción de los componentes del portal de BAM. Para obtener una descripción más detallada, consulte los temas enumerados en la sección Consulte también.  
  
### <a name="activity-searches"></a>Búsquedas de actividad  
 El portal de BAM se utiliza para realizar búsquedas con respecto a los datos de BAM para encontrar una actividad específica de BAM. Se crean consultas al agregar y quitar cláusulas de búsqueda que le permiten mostrar las actividades que coinciden con los criterios de los que desea recibir una alerta.  
  
 Las consultas se pueden guardar y volver a usar. También pueden ser la base para una alerta, como una notificación cuando un pedido llega desde un cliente específico.  
  
### <a name="aggregations"></a>Agregaciones  
 El portal le permite capturar una instantánea de los datos y mostrarlos en forma de diagrama gráfico y diagrama de tabla dinámica que lo acompaña. Estos datos le proporcionan visibilidad en el estado de ese proceso o del negocio en general. Por ejemplo, puede que un usuario desee ver un gráfico circular básico que muestre un desglose de 1.000 facturas recibidas en un día en lo que respecta a la fase de procesamiento que se alcanzado con cada factura (400 en “evaluación”, 400 rechazadas, 100 pagadas y 100 en “asignación de recursos”).  
  
 Los datos que se presentan pueden ser la base para crear una alerta, como “Notifíqueme si alguna vez hay más de 500 facturas en la fase de 'evaluación' del proceso.”  
  
### <a name="alert-manager"></a>Administrador de alertas  
 El portal proporciona una interfaz de usuario para crear alertas y editar alertas existentes. Las alertas llevan las condiciones que se van a supervisar desde la página Búsqueda de actividad o la página Agregaciones. El administrador de alertas es donde se cumplimentan las partes correspondientes de una alerta, como a quién se notifica, cómo se notifica (por ejemplo, mediante correo electrónico) o si otros usuarios podrán ver las alertas y suscribirse a ellas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Componentes del Portal de BAM](../core/components-of-the-bam-portal.md)  
  
-   [Planeación del Portal de BAM](../core/planning-for-the-bam-portal.md)  
  
-   [Búsquedas de actividad en el Portal de BAM](../core/activity-searches-in-the-bam-portal.md)  
  
-   [Agregaciones del Portal de BAM](../core/aggregations-in-the-bam-portal.md)  
  
-   [Alertas del Portal de BAM](../core/alerts-in-the-bam-portal.md)  
  
-   [Accesibilidad para el Portal de BAM](../core/accessibility-for-the-bam-portal.md)  
  
-   [Consideraciones de seguridad para el Portal de BAM](../core/security-considerations-for-the-bam-portal.md)  
  
-   [Problemas conocidos del Portal de BAM](../core/known-issues-in-the-bam-portal.md)  
  
## <a name="see-also"></a>Vea también  
 [Búsqueda de actividad en el Portal de BAM página](../core/activity-search-on-the-bam-portal-page.md)   
 [Las agregaciones en el Portal de BAM página](../core/aggregations-on-the-bam-portal-page.md)   
 [Alert Manager en el Portal de BAM de página](../core/alert-manager-on-the-bam-portal-page.md)