---
title: "Solución de problemas de rendimiento de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dbf21fb9-1ae1-48b5-a65a-e96839b23945
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21003c4d3565158945e91371fa760cf97692b472
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshooting-biztalk-server-performance"></a>Solucionar problemas de rendimiento de BizTalk Server
Esta sección contiene directrices generales para diagnosticar y resolver problemas de rendimiento relacionados con el motor de mensajería de BizTalk.  
  
## <a name="estimating-document-processing-requirements"></a>Estimar los requisitos de procesamiento de un documento  
 Planee y realice pruebas para determinar las necesidades de rendimiento de su motor de mensajería antes de implementar su solución en un entorno de producción. Esto le ayudará a crear sus entornos de BizTalk Server y SQL Server de la forma correcta.  
  
1.  Incluya en sus planes capacidad para afrontar sobrecargas asociadas con sus necesidades de tolerancia a errores y copia de seguridad y recuperación  
  
    -   ¿Se van a configurar los discos de SQL Server como matrices RAID?  
  
    -   ¿Se va a usar la organización por clústeres de Windows para los hosts de BizTalk, SQL Server o Inicio de sesión único empresarial? Para obtener más información, consulte [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).  
  
    -   ¿Se usará el equilibrio de carga de red?  
  
    -   ¿Cuáles son los requisitos de copia de seguridad y de recuperación del entorno? Para obtener más información, consulte [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md).  
  
2.  Siga las instrucciones de [planear el rendimiento sostenido de](../core/planning-for-sustained-performance.md) para planear, probar y escalar el entorno de BizTalk Server y SQL Server.  
  
3.  Siga las instrucciones de [características de rendimiento de seguimiento](../core/tracking-performance-characteristics.md) planear para afrontar sobrecargas relacionadas con requisitos de seguimiento de documentos.  
  
## <a name="optimizing-an-existing-biztalk-server-environment"></a>Optimizar un entorno existente de BizTalk Server  
 Siga estos pasos para optimizar un entorno existente de BizTalk Server:  
  
1.  Siga las instrucciones de [identificar cuellos de botella de rendimiento](../core/identifying-performance-bottlenecks.md) para identificar los posibles cuellos de botella en su entorno de BizTalk Server.  
  
2.  Siga las instrucciones de [optimizar recursos a través de Host de límite de uso](../core/optimizing-resource-usage-through-host-throttling.md) para maximizar el rendimiento de documento para el entorno de BizTalk Server.  
  
3.  Considere la posibilidad de modificar los parámetros mencionados en [parámetros de configuración que afectan al rendimiento del adaptador](../core/configuration-parameters-that-affect-adapter-performance.md) para maximizar el rendimiento del adaptador en ciertos escenarios.  
  
4.  Siga las instrucciones de [cómo BizTalk Server procesa grandes mensajes](../core/how-biztalk-server-processes-large-messages.md) para optimizar el rendimiento de motor de mensajería al procesar mensajes de gran tamaño (más de 100 MB).  
  
5.  Cree hosts e instancias de host distintos para adaptadores de envío, adaptadores de recepción y orquestaciones. Esto le dará a cada adaptador una instancia de host distinta en la que ejecutarse y garantizará que los adaptadores no interfieran unos con otros. Como los valores de limitación de host son configurables en el nivel de hosts, la separación de la lógica de procesamiento en hosts diferentes también le permitirá configurar los valores de limitación según los requisitos de procesamiento de cada host.  
  
## <a name="diagnosing-performance-problems-in-an-existing-biztalk-server-environment"></a>Diagnosticar problemas de rendimiento en un entorno existente de BizTalk Server  
 Normalmente un problema de rendimiento puede localizarse en uno de los siguientes componentes del entorno de BizTalk Server:  
  
-   Un adaptador de recepción o el sistema del que el adaptador está recibiendo documentos. Por ejemplo, si el adaptador de HTTP está recibiendo documentos a una velocidad mejorable, puede que el problema se encuentre en el adaptador de recepción de HTTP o en el cliente que está enviando a dicho adaptador.  
  
-   Una instancia de servicio de orquestación.  
  
-   El rendimiento del servidor Microsoft SQL Server que aloja las bases de datos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Un adaptador de envío o el sistema al que el adaptador está enviando documentos. Por ejemplo, si el adaptador de SQL está enviando documentos a una velocidad mejorable, puede que el problema se encuentre en el adaptador de envío de SQL o en el equipo que ejecuta el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que el adaptador de SQL está actualizando.  
  
 Use las siguientes directrices como ayuda para identificar los componentes del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuyo rendimiento es insuficiente:  
  
-   Capture las advertencias o los errores que se generen en el Visor de eventos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
-   Siga los pasos de [identificar cuellos de botella de rendimiento](../core/identifying-performance-bottlenecks.md) para ayudar a identificar los cuellos de botella de rendimiento.  
  
 Una vez identificado el componente que no rinde satisfactoriamente, siga las directrices correspondientes para resolver el problema:  
  
 **Directrices para solucionar problemas de rendimiento relacionados con los adaptadores de recepción y envío**  
  
-   Vea [solución de problemas de adaptadores de BizTalk Server](../core/troubleshooting-biztalk-server-adapters.md) para obtener información general solucionar problemas relacionados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores. Esta sección contiene información general para la solución de problemas, lo que incluye información sobre cómo configurar la creación de registros para ciertos adaptadores e información utilizable para diagnosticar problemas de red, de MSDTC, del Registro, del sistema de archivos y de IIS.  
  
-   Consulte la sección correspondiente de [solución de problemas de dependencias de BizTalk Server](../core/troubleshooting-biztalk-server-dependencies.md) para obtener información general solucionar problemas con MSDTC, certificados, Enterprise Single Sign-On, y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
 **Directrices para solucionar problemas de rendimiento relacionados con orquestaciones**  
  
-   Modifique las secciones correspondientes del archivo BTSNTSvc.exe.config que se documentan en [configuración del motor de orquestación](../core/orchestration-engine-configuration.md).  
  
 **Directrices para solucionar problemas de rendimiento relacionados con SQL Server**  
  
-   El Analizador de SQL Server se puede utilizar para capturar instrucciones Transact-SQL enviadas al servidor SQL Server y conjuntos de resultados de SQL Server de estas instrucciones. Ya que BizTalk Server está integrado estrechamente con el servidor SQL Server, el análisis de la traza del Analizador de SQL Server puede ser una herramienta útil para analizar problemas que se puedan producir en BizTalk Server al leer o escribir a bases de datos del servidor SQL Server. Para obtener información acerca del uso del Analizador de SQL Server, vea la documentación de SQL Server.  
  
-   El Editor de consultas de SQL Server puede utilizarse para ejecutar instrucciones SQL directamente en las bases de datos de SQL Server. Esta funcionalidad puede resultar útil para realizar consultas en las bases de datos de BizTalk Server o para actualizarlas en determinados escenarios. Para obtener más información sobre el Editor de consultas, consulte la documentación de SQL Server.  
  
-   Revisión [solución de problemas de SQL Server](../core/troubleshooting-sql-server.md) para obtener información adicional.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas](../core/troubleshooting.md)