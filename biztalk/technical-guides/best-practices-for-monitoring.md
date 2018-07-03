---
title: Procedimientos recomendados para la supervisión | Microsoft Docs
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
ms.openlocfilehash: 9bfb2b5575fe46c1104ddc6b852695fb777275ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981661"
---
# <a name="best-practices-for-monitoring"></a>Procedimientos recomendados para la supervisión
En este tema proporciona prácticas recomendadas para la supervisión de su entorno de Microsoft BizTalk Server y las aplicaciones.  
  
 **Crear y, a continuación, implementar un plan de supervisión para la infraestructura y aplicaciones de BizTalk**  
  
- Lea los temas de supervisión en esta guía para garantizar una solución de supervisión más completa. Factores a considerar incluyen lo siguiente:  
  
  -   ¿Quién llevará a cabo la diaria, semanal, mensual y como las tareas de supervisión necesarias?  
  
  -   ¿Es alguien una notificación de eventos, los mensajes suspendidos u otros errores de sistema o una aplicación?  
  
  -   ¿"Esperadas" excepciones filtrada o dada una prioridad más baja?  
  
  -   ¿Son que todas supervisadas para asegurarse de que continúan la ejecución de instancias de host?  
  
  -   ¿Son todos los servicios personalizados, los registros de eventos personalizados y bases de datos personalizadas que supervisan?  
  
  -   ¿Son los equipos de SQL Server y el Agente SQL Server de BizTalk los trabajos que se supervisan?  
  
  **Si es posible, instalar una aplicación de supervisión como [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] con el fin de automatizar la supervisión de su infraestructura y aplicaciones de BizTalk Server**  
  
- Uso de Microsoft System Center Operations Manager es el método preferido para la supervisión automatizada porque los módulos de administración de BizTalk Server proporcionan centenares de reglas integradas de BizTalk Server.  
  
   Para obtener más información, vea los recursos siguientes:  
  
  -   [Módulo de administración de Microsoft BizTalk Server para System Center Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=190339) (http://go.microsoft.com/fwlink/?LinkID=190339).  
  
  -   [Cómo importar un módulo de administración en Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=98348) ()http://go.microsoft.com/fwlink/?LinkID=98348)  
  
  -   [Cómo marcar las bases de datos de BizTalk Server para la supervisión personalizada](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
  **Ejecutar servidor BizTalk Server Best Practices Analyzer**  
  
- BizTalk Server Best Practices Analyzer examina la implementación de BizTalk Server y genera una lista de problemas relacionados con los estándares de prácticas recomendados. La herramienta realiza la comprobación de nivel de configuración mediante la recopilación de datos de orígenes de información diferente, como las clases de Instrumental de administración de Windows (WMI), las bases de datos de SQL Server y las entradas del registro. Los datos, a continuación, se utilizan para evaluar la configuración de implementación. La herramienta lee solo para informes y no modifica cualquier configuración del sistema y no es una herramienta de ajuste automático.  
  
   Puede descargar BizTalk Server Best Practices Analyzer en [ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317).  
  
  **Ejecute la herramienta de análisis de registros de rendimiento (PAL)**  
  
- Está disponible como descarga gratuita en PAL [ https://github.com/clinthuffman/PAL ](https://github.com/clinthuffman/PAL). Para obtener información importante de instalación, consulte [mediante la herramienta de análisis de rendimiento de los registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).  
  
  **Ejecutar el analizador de registros**  
  
- Log Parser es una herramienta eficaz y versátil que ofrece acceso universal de consulta a datos basados en texto tales como archivos de registro, archivos XML y archivos CSV, así como orígenes de datos clave en el sistema de operativo Windows® como el registro de eventos, el registro, el sistema de archivos y activo Directory®. Es posible que desee usar esta herramienta para consultar una cantidad significativa de información de registro. Puede descargar la herramienta Log Parser en [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)  
  
  **Ejecute la herramienta BizTalk MsgBoxViewer**  
  
  Ejecute el [herramienta BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151930) disponibles desde [ http://go.microsoft.com/fwlink/?LinkId=151930 ](http://go.microsoft.com/fwlink/?LinkId=151930). Esta herramienta analiza BizTalk MessageBox y otras bases de datos y genera un informe HTML que contiene las advertencias, si cualquier y otra información relacionada con las bases de datos. También puede guardar los informes para su uso posterior. Estos informes pueden ser útiles al solucionar problemas con la aplicación de BizTalk.  
  
  Si la herramienta BizTalk MsgBoxViewer identifica cualquier problema, ejecute el [herramienta terminador](http://go.microsoft.com/fwlink/?LinkId=151931) disponible en [ http://go.microsoft.com/fwlink/?LinkId=151931 ](http://go.microsoft.com/fwlink/?LinkId=151931). Esta herramienta permite a los usuarios fácil de resolver los problemas detectados por la herramienta BizTalk MsgBoxViewer. Para obtener más información acerca de cómo la herramienta terminador se integra con la herramienta BizTalk MsgBoxViewer, consulte [utilizando el terminador de BizTalk para resolver los problemas identificados por BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932).  
  
> [!NOTE]  
>  Uso de estas herramientas no es compatible con Microsoft y Microsoft no ofrece ninguna garantía sobre la idoneidad de estos programas. El uso de estos programas queda bajo su propia responsabilidad.  
  
 **Realizar supervisión de una prioridad**  
  
-   Una supervisión constante de la infraestructura y aplicaciones de BizTalk Server es esencial para mantener un entorno correcto.  
  
-   Periódicamente, evaluar y ajustar sus herramientas de supervisión con el tiempo y como las aplicaciones de BizTalk Server y el cambio en la infraestructura.