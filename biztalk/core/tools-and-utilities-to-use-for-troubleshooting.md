---
title: "Herramientas y utilidades que se usan para la solución de problemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c817384f-e328-439d-9c41-a94ed75670ce
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15030040702b8c9150681b5ff31449d6c4c299d0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="tools-and-utilities-to-use-for-troubleshooting"></a>Herramientas y utilidades que se utilizan para solucionar problemas
Esta sección describen varias herramientas y utilidades que pueden resultar útiles para diagnosticar la causa de un problema en una dependencia o un componente de Microsoft BizTalk Server.  
  
## <a name="event-viewer"></a>Visor de eventos  
 BizTalk Server registra información, advertencias y errores en el registro de eventos de BizTalk Server basado en equipo. Cuando se solucionan problemas en una dependencia o un componente de BizTalk Server, los registros de eventos debe ser el primer lugar para buscar información ayudar a diagnosticar el problema. 
  
## <a name="network-monitor"></a>Monitor de red  
 Use la utilidad Monitor de red para capturar el tráfico de red entre servidores y clientes remotos y BizTalk Server. Se puede analizar el tráfico de red capturado para diagnosticar los problemas relacionados con la red.  
  
 Monitor de red está disponible en Windows Server.  
  
 La funcionalidad del monitor de red se proporciona para Windows XP a través de la utilización de la utilidad NETCAP.exe que se instala con las herramientas de soporte técnico de Windows que se encuentran en el CD de Windows XP. Para obtener más información acerca de la utilidad NETCAP.exe, consulte [descripción de la utilidad de captura de Monitor de red](http://go.microsoft.com/fwlink/?LinkId=66227).  
  
 Para obtener información acerca de cómo capturar el tráfico de red con Monitor de red vea [cómo capturar el tráfico de red con Monitor de red](http://go.microsoft.com/fwlink/?LinkId=66230).  
  
## <a name="fiddler-tool"></a>Herramienta Fiddler  
 Use Fiddler para registrar todo el tráfico HTTP entre el servidor BizTalk Server y servidores o clientes remotos. Fiddler es compatible con Visual Studio Team Edition para evaluadores y permite guardar grabaciones como archivos de prueba Web que se pueden agregar a Visual Studio Team Edition para proyectos de evaluadores.  
  
 Los inconvenientes de Fiddler son que no es compatible actualmente con SSL, no realiza el seguimiento automático de campos ocultos, por ejemplo, ViewState y no filtra las solicitudes dependientes.  
  
 Fiddler está disponible en [http://www.fiddlertool.com](http://go.microsoft.com/fwlink/?LinkId=119605). 
  
## <a name="sql-server-profiler"></a>SQL Server Profiler  
 Microsoft SQL Server Profiler puede usarse para capturar instrucciones Transact-SQL que se envían a SQL Server y conjuntos de resultados de SQL Server de estas instrucciones. Ya que BizTalk Server está integrado estrechamente con el servidor SQL Server, el análisis de la traza del Analizador de SQL Server puede ser una herramienta útil para analizar problemas que se puedan producir en BizTalk Server al leer o escribir a bases de datos del servidor SQL Server. 
  
## <a name="sql-server-query-editor"></a>Editor de consultas de SQL Server  
 El editor de consultas de SQL Server se puede usar para ejecutar sentencias SQL directamente en bases de datos de SQL Server. Esta funcionalidad puede resultar útil para realizar consultas en las bases de datos de BizTalk Server o para actualizarlas en determinados escenarios. 
  
## <a name="dtctester"></a>DTCTester  
 La mayoría de las operaciones en tiempo de ejecución de BizTalk Server necesitan ser compatibles con Microsoft Distributed Transaction Coordinator (MSDTC) para asegurar que las operaciones coincidan con respecto a las transacciones. Si la compatibilidad de la transacción MSDTC no está disponible, las operaciones en tiempo de ejecución de BizTalk Server asociadas no pueden continuar. Utilice la herramienta DTCTester para comprobar la admisión de transacciones distribuidas en dos firewalls o en las redes. La utilidad DTCTester utiliza ODBC para comprobar la admisión de transacciones con respecto a una base de datos de SQL Server y, por lo tanto, requiere que SQL Server esté instalado en uno de los equipos que se van a comprobar. Para obtener más información acerca de DTCTester, vea [cómo utilizar la herramienta DTCTester](http://support.microsoft.com/kb/293799).  
  
## <a name="dtcping"></a>DTCPing  
 Utilice la herramienta DTCPing para comprobar la admisión de transacciones distribuidas en dos firewalls o con respecto a las redes. La herramienta DTCPing se debe instalar tanto en el equipo cliente como en el equipo servidor y se trata de una buena alternativa a la utilidad DTCTester cuando SQL Server no se ha instalado en ningún equipo. Para obtener más información sobre el uso de DTCPing para comprobar la compatibilidad con transacciones distribuidas vea [cómo solucionar problemas de firewall de MS DTC](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues).  
  
## <a name="performance-console"></a>Consola Rendimiento  
 Utilice la consola Rendimiento para capturar los datos de supervisión de rendimiento de su entorno de BizTalk Server. Vea [contadores de rendimiento](../core/performance-counters.md) para obtener una lista completa de los contadores de rendimiento incluidos con BizTalk Server. 
  
## <a name="regmon-filemon-and-debugview"></a>RegMon, FileMon, y DebugView  
 RegMon muestra la actividad de acceso al Registro en tiempo real, enumerando cada llamada al Registro que una aplicación realiza y registrando el resultado. Esta herramienta le permite identificar cuándo una aplicación no puede obtener acceso a la clave del Registro. Del mismo modo, FileMon muestra la actividad del sistema de archivos en tiempo real, enumerando cada llamada que la aplicación realiza y registrando el resultado. Debugview le permite supervisar el resultado de depuración en su sistema local, o en cualquier equipo en red al que pueda llegar mediante TCP/IP.  
  
 RegMon y FileMon permite que los administradores puedan probar una aplicación e identificar los errores que se pueden producir de las llamadas que realiza la aplicación al Registro o al sistema de archivos. El administrador puede corregir el error al cambiar los permisos del sistema de archivos o de la clave del Registro, por ejemplo.  
  
 DebugView permite que los administradores puedan probar una aplicación y supervisar el resultado de depuración en su sistema local o en cualquier equipo en red al que pueda llegar mediante TCP/IP.  
  
 Para obtener más información acerca de estas utilidades, consulte [Windows Sysinternals](https://docs.microsoft.com/sysinternals/). 
  
## <a name="debug-diagnostics-tool-of-the-iis-diagnostics-toolkit"></a>Herramienta de diagnósticos de depuración del Kit de herramientas de diagnóstico de IIS  
 La herramienta de diagnóstico de depuración del Kit de herramientas de diagnóstico de IIS puede generar un volcado de memoria de los procesos que han registrado errores y realizar un análisis básico del archivo de vaciado generado. Para obtener más información acerca de cómo utilizar la herramienta de diagnóstico de depuración del Kit de herramientas de diagnóstico de IIS para capturar un volcado de memoria, vea [cómo capturar un volcado de memoria de un proceso de BizTalk](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md).