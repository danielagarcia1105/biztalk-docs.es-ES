---
title: Prácticas recomendadas para la supervisión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b3d4761c32123db53ea35daf91d0f13d9a2488
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008533"
---
# <a name="best-practices-for-monitoring"></a>Prácticas recomendadas para la supervisión
Este tema proporciona prácticas recomendadas para la supervisión de su entorno de Microsoft BizTalk Server y las aplicaciones.  
  
 **Crear y, a continuación, implementar un plan de supervisión de las aplicaciones de BizTalk y la infraestructura**  
  
-   Lea los temas de supervisión en esta guía para garantizar una solución de supervisión más completa. Factores a tener en cuenta son los siguientes:  
  
    -   ¿Quién llevará a cabo diariamente, semanalmente, mensualmente y como tareas de supervisión necesarios?  
  
    -   ¿Es un usuario recibe una notificación de eventos, mensajes suspendidos u otros errores de aplicación o del sistema?  
  
    -   ¿Son "esperadas" excepciones filtrada o debido a una prioridad más baja?  
  
    -   ¿Son que todas las instancias supervisados para garantizar que siguen ejecutándose de host?  
  
    -   ¿Son todos los servicios personalizados, registros de eventos personalizados y bases de datos personalizadas supervisados?  
  
    -   ¿Son los equipos de SQL Server y el Agente SQL Server de BizTalk supervisados los trabajos?  
  
 **Si es posible, instale una aplicación de supervisión como [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] con el fin de automatizar la supervisión de la infraestructura y aplicaciones de BizTalk Server**  
  
-   Con Microsoft System Center Operations Manager es el método preferido para la supervisión automatizada porque los módulos de administración de BizTalk Server proporcionan centenares de reglas integradas para BizTalk Server.  
  
     Para obtener más información, vea los recursos siguientes:  
  
    -   [Módulo de administración de Microsoft BizTalk Server para System Center Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=190339) (http://go.microsoft.com/fwlink/?LinkID=190339).  
  
    -   [Cómo importar un módulo de administración en Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=98348) (http://go.microsoft.com/fwlink/?LinkID=98348)  
  
    -   [Cómo marcar las bases de datos de BizTalk Server para la supervisión personalizada](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
 **Ejecutar el analizador de procedimientos recomendados de BizTalk Server**  
  
-   BizTalk Server Best Practices Analyzer examina una implementación de BizTalk Server y genera una lista de problemas relacionados con los estándares de prácticas recomendados. La herramienta realiza la comprobación de nivel de configuración mediante la recopilación de datos de orígenes de información diferente, como las clases de Instrumental de administración de Windows (WMI) y las bases de datos de SQL Server, las entradas del registro. Los datos, a continuación, se utilizan para evaluar la configuración de implementación. La herramienta lee solo informes y no modifica cualquier configuración del sistema y no es una herramienta de optimización automática.  
  
     Puede descargar el analizador de procedimientos recomendados de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317).  
  
 **Ejecutar la herramienta de análisis de registros de rendimiento (PAL)**  
  
-   Está disponible como descarga gratuita en PAL [https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL). Para obtener información importante de instalación, consulte [mediante la herramienta de análisis de rendimiento de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).  
  
 **Ejecutar el analizador del registro**  
  
-   Analizador del registro es una herramienta eficaz y versátil que proporciona acceso universal de consulta a datos basados en texto, como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en el sistema de operativo Windows® como el registro de eventos, el registro, el sistema de archivos y Active Directory®. Puede usar esta herramienta para consultar una cantidad significativa de información de registro. Puede descargar la herramienta de analizador del registro en [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)  
  
 **Ejecutar la herramienta BizTalk MsgBoxViewer**  
  
 Ejecute el [herramienta BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151930) disponibles en [http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930). Esta herramienta analiza BizTalk MessageBox y otras bases de datos y genera un informe HTML que contiene advertencias, si cualquier y otra información relacionada con las bases de datos. También puede guardar los informes para su uso posterior. Estos informes pueden ser útiles al solucionar problemas relacionados con la aplicación de BizTalk.  
  
 Si la herramienta de BizTalk MsgBoxViewer identifica los problemas, ejecute el [herramienta terminador](http://go.microsoft.com/fwlink/?LinkId=151931) disponible en [http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931). Esta herramienta permite a los usuarios a resolver fácilmente los problemas identificados por la herramienta de BizTalk MsgBoxViewer. Para obtener más información acerca de cómo la herramienta de terminador se integra con la herramienta de BizTalk MsgBoxViewer, consulte [utilizando el terminador de BizTalk para resolver los problemas identificados por BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932).  
  
> [!NOTE]  
>  Uso de estas herramientas no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de estos programas. El uso de estos programas queda bajo su propia responsabilidad.  
  
 **Asegúrese de supervisar una prioridad**  
  
-   Supervisión coherente de infraestructura y las aplicaciones de BizTalk Server es esencial para mantener un entorno correcto.  
  
-   Periódicamente, evaluar y ajustar sus herramientas de supervisión con el tiempo y que las aplicaciones de BizTalk Server y el cambio en la infraestructura.