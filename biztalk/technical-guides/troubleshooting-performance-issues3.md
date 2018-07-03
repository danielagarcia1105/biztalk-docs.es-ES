---
title: Solución de problemas de rendimiento de los clientes3 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a348c4b-7df2-43e9-810c-1f538a97d7e1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40f7ae950a7078152d2952fb72ebe39303d41813
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998813"
---
# <a name="troubleshooting-performance-issues"></a>Solucionar problemas de rendimiento
Esta sección contiene directrices generales para diagnosticar y resolver problemas de rendimiento relacionados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y sus dependencias. Estas instrucciones también pueden utilizarse de forma preventiva, identificar posibles problemas antes de que se conviertan en problemas críticos.  
  
## <a name="diagnosing-performance-problems-in-the-biztalk-server-environment"></a>Diagnosticar problemas de rendimiento en el entorno de BizTalk Server  
 Normalmente, un problema de rendimiento puede localizarse en uno de los siguientes componentes de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno:  
  
- Un adaptador de recepción o el sistema desde el que el adaptador está recibiendo documentos. Por ejemplo, si se reciben documentos por el adaptador HTTP a una velocidad Mejorable, puede ser el problema con HTTP del adaptador de recepción o con el cliente que está publicando para el adaptador de HTTP.  
  
- Una instancia de servicio de orquestación.  
  
- Rendimiento de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que hospeda el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
- Un adaptador de envío o el sistema al que el adaptador está enviando documentos. Por ejemplo, si se va a enviar documentos por el adaptador SQL a una velocidad Mejorable, a continuación, el problema puede ser con el adaptador de envío SQL o con el equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que se está actualizando el adaptador de SQL.  
  
  Use las siguientes directrices como ayuda para identificar los componentes del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuyo rendimiento es insuficiente:  
  
- Capture las advertencias o los errores que se generen en el Visor de eventos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
- Siga los pasos descritos en "Identificación de cuellos de botella de rendimiento" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154238 ](http://go.microsoft.com/fwlink/?LinkId=154238) para ayudar a identificar los cuellos de botella de rendimiento.  
  
  Una vez identificado el componente que no rinde satisfactoriamente, siga las directrices correspondientes para resolver el problema:  
  
  **Directrices para solucionar problemas de rendimiento relacionados con los adaptadores de recepción y envío**  
  
- Para obtener información sobre cómo solucionar problemas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores, vea "Solución de problemas de los adaptadores de BizTalk Server" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154240 ](http://go.microsoft.com/fwlink/?LinkId=154240). Esta sección contiene información general de solución de problemas incluida información acerca de cómo configurar el registro para determinados adaptadores e información que se puede usar diagnosticar problemas de red, problemas con MSDTC, problemas con el registro, problemas con el archivo sistema y problemas con IIS.  
  
- Para obtener información acerca de cómo solucionar problemas con MSDTC, certificados, Enterprise Single Sign-On, y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], consulte la sección correspondiente de "Solución de problemas de dependencias de servidor de BizTalk" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154242 ](http://go.microsoft.com/fwlink/?LinkId=154242).  
  
  **Directrices para solucionar problemas de rendimiento relacionados con orquestaciones**  
  
- Para obtener información acerca de cómo modificar las secciones correspondientes del archivo BTSNTSvc.exe.config, consulte "Configuración del motor de orquestación" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154244 ](http://go.microsoft.com/fwlink/?LinkId=154244).  
  
  **Directrices para solucionar problemas de rendimiento relacionados con SQL Server**  
  
- Se puede usar SQL Server Profiler para capturar instrucciones Transact-SQL que se envían a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] conjuntos de resultados de estas instrucciones. Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está estrechamente integrado con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], el análisis de un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] traza del analizador puede ser una herramienta útil para analizar problemas que pueden producirse en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] al leer y escribir en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos. Para obtener información sobre cómo usar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler, vea "Uso de SQL Server Profiler" en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla en [ http://go.microsoft.com/fwlink/?linkid=104423 ](http://go.microsoft.com/fwlink/?linkid=104423).  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio puede utilizarse para ejecutar instrucciones SQL directamente en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos. Esta funcionalidad puede ser útil para consultar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o para actualizar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en determinados escenarios. Para obtener más información sobre el uso de SQL Server Management Studio para ejecutar instrucciones SQL, vea "Escribir, analizar y modificar Scripts con SQL Server Management Studio" en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla en [ http://go.microsoft.com/fwlink/?linkid=104425 ](http://go.microsoft.com/fwlink/?linkid=104425).  
  
- Para obtener más información acerca de cómo resolver el problema de rendimiento relacionados con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea "Solución de problemas de SQL Server" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=154250 ](http://go.microsoft.com/fwlink/?LinkId=154250).  
  
## <a name="see-also"></a>Vea también  
 [http://go.microsoft.com/fwlink/?linkid=104430](http://go.microsoft.com/fwlink/?linkid=104430)