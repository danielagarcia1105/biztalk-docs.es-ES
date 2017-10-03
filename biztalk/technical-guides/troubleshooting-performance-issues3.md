---
title: "Solución de problemas de rendimiento de los clientes3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a348c4b-7df2-43e9-810c-1f538a97d7e1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93f5aad28eb31b51122be4c17de6ab92e8244a5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-performance-issues"></a>Solucionar problemas de rendimiento
Esta sección contiene directrices generales para diagnosticar y resolver problemas de rendimiento relacionados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y sus dependencias. Estas instrucciones también pueden utilizarse de forma preferente, para identificar posibles problemas antes de que resulten más críticos.  
  
## <a name="diagnosing-performance-problems-in-the-biztalk-server-environment"></a>Diagnosticar problemas de rendimiento en el entorno de BizTalk Server  
 Normalmente un problema de rendimiento puede localizarse en uno de los siguientes componentes de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno:  
  
-   Un adaptador de recepción o el sistema desde el que el adaptador está recibiendo documentos. Por ejemplo, si está recibiendo documentos por el adaptador HTTP a una velocidad Mejorable, a continuación, el problema puede estar relacionado con HTTP adaptador de recepción o con el cliente que está publicando para el adaptador de HTTP.  
  
-   Una instancia de servicio de orquestación.  
  
-   Rendimiento de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que hospeda el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
-   Un adaptador de envío o el sistema al que el adaptador está enviando documentos. Por ejemplo, si los documentos que se envían mediante el adaptador de SQL a una velocidad Mejorable, a continuación, el problema puede ser el adaptador de envío SQL o con el equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que se está actualizando el adaptador de SQL.  
  
 Use las siguientes directrices como ayuda para identificar los componentes del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuyo rendimiento es insuficiente:  
  
-   Capture las advertencias o los errores que se generen en el Visor de eventos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
-   Siga los pasos descritos en "Identificación de cuellos de botella de rendimiento" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154238](http://go.microsoft.com/fwlink/?LinkId=154238) para ayudar a identificar los cuellos de botella de rendimiento.  
  
 Una vez identificado el componente que no rinde satisfactoriamente, siga las directrices correspondientes para resolver el problema:  
  
 **Directrices para solucionar problemas de rendimiento relacionados con los adaptadores de recepción y envío**  
  
-   Para obtener información acerca de cómo solucionar problemas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores, vea "Solucionar problemas de los adaptadores de BizTalk Server" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154240](http://go.microsoft.com/fwlink/?LinkId=154240). Esta sección contiene información general de solución de problemas incluida información acerca de cómo configurar el registro para ciertos adaptadores e información que se puede usar diagnosticar problemas de red, problemas con MSDTC, problemas con el registro de problemas con el archivo sistema y problemas con IIS.  
  
-   Para obtener información acerca de cómo solucionar problemas con MSDTC, certificados, Enterprise Single Sign-On, y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], consulte la sección correspondiente de "Solución de problemas de dependencias de servidor de BizTalk" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http:// ¿go.Microsoft.com/fwlink/? LinkId = 154242](http://go.microsoft.com/fwlink/?LinkId=154242).  
  
 **Directrices para solucionar problemas de rendimiento relacionados con orquestaciones**  
  
-   Para obtener información acerca de cómo modificar las secciones correspondientes del archivo BTSNTSvc.exe.config, consulte "Configuración del motor de orquestación" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154244](http://go.microsoft.com/fwlink/?LinkId=154244).  
  
 **Directrices para solucionar problemas de rendimiento relacionados con SQL Server**  
  
-   Analizador de SQL Server puede usarse para capturar instrucciones Transact-SQL que se envían a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] conjuntos de resultados de estas instrucciones. Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está totalmente integrado con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], el análisis de un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] traza del analizador puede ser una herramienta útil para analizar problemas que pueden producirse en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] al leer y escribir en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos. Para obtener información sobre cómo usar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] generador de perfiles, vea "Usar el analizador de SQL Server" en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/?linkid=104423](http://go.microsoft.com/fwlink/?linkid=104423).  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio puede utilizarse para ejecutar instrucciones SQL directamente en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos. Esta funcionalidad puede ser útil para consultar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en determinados escenarios. Para obtener más información acerca del uso de SQL Server Management Studio para ejecutar instrucciones SQL, vea "Escribir, analizar y editar Scripts con SQL Server Management Studio" en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla en [http://go.microsoft.com/fwlink/? LinkId = 104425](http://go.microsoft.com/fwlink/?linkid=104425).  
  
-   Para obtener más información acerca de cómo resolver el problema de rendimiento relacionado con la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea "Solucionar problemas de SQL Server" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=154250](http://go.microsoft.com/fwlink/?LinkId=154250).  
  
## <a name="see-also"></a>Vea también  
 [http://go.Microsoft.com/fwlink/?LinkId=104430](http://go.microsoft.com/fwlink/?linkid=104430)