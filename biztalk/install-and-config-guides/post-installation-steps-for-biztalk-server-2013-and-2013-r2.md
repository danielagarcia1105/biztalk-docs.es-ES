---
title: Los pasos posteriores a la instalación de BizTalk Server 2013 y 2013 R2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83215952b28da21e143af118c31519cd31fca911
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978701"
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a>Pasos posteriores a la instalación de BizTalk Server 2013 y 2013 R2
  
##  <a name="BKMK_NamedPipes"></a> Habilitar TCP/IP y canalizaciones con nombre  
  
1. Abra el **Administrador de configuración de SQL Server**.  
  
2. Expanda **Configuración de red de SQL Server** y seleccione **Protocolos para MSSQLSERVER**.  
  
3. Compruebe que están habilitadas las opciones **TCP/IP** y **Canalizaciones con nombre**. Si están habilitadas, continúe en el paso siguiente.  
  
    Si no están habilitadas:  
  
   -   Haga clic con el botón derecho en el protocolo y, después, haga clic en **Habilitar**.  
  
   -   Repita los pasos para habilitar el otro protocolo, si fuera necesario.  
  
   -   En el panel izquierdo, haga clic en **Servicios de SQL Server**.  
  
   -   En el panel derecho, haga clic con el botón derecho en **SQL Server (MSSQLSERVER)** y, después, haga clic en **Detener**.  
  
   -   Después de detener el servicio, haga clic con el botón derecho en **SQL Server (MSSQLSERVER)** y haga clic en **Iniciar**.  
  
   > [!IMPORTANT]
   >  Si usa [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], puede que el servicio **NS$BAMAlerts** se detenga. Reiniciar el servicio.  
  
4. Cierre el **Administrador de configuración**.  
  
##  <a name="BKMK_DTC"></a> Habilitar el DTC en el servidor de host local  
  
1. Abra Servicios de componentes:  
  
    **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: pulse la tecla Windows y escriba **Servicios de componentes**. En la ventana Resultados, seleccione **Servicios de componentes**.  
  
    **Windows 8.1**: pulse la tecla Windows y escriba **Herramientas administrativas**. En la ventana Buscar, seleccione **Configuración**. En la ventana Resultados, haga clic en **Herramientas administrativas**. Haga doble clic en **Servicios de componentes**.  
  
    **Windows 7 SP1**: seleccione **Inicio**. En el cuadro de texto **Buscar**, escriba **Servicios de componentes** y haga clic en él para abrirlo.  
  
2. En el árbol de consola, expanda **Servicios de componentes**, **Equipos**, **Mi PC**, **Coordinador de transacciones distribuidas** y, después, haga clic en **DTC local**.  
  
3. Haga clic con el botón derecho en **DTC local** y seleccione **Propiedades** para abrir el cuadro de diálogo **Propiedades: DTC local**.  
  
4. Seleccione la pestaña **Seguridad**.  
  
5. Compruebe que están seleccionadas las siguientes opciones:  
  
   - **Acceso a DTC desde la red**  
  
   - **Permitir entrantes**  
  
   - **Permitir salientes**  
  
   - **No se requiere autenticación**  
  
     Para conocer otras opciones necesarias, consulte [Solucionar problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).  
  
6. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Propiedades: DTC local**. Reinicie el servicio MSDTC si se le pide.  
  
7. Cierre **Servicios de componentes**.  
  
##  <a name="BKMK_Firewall"></a> Configurar el Firewall de Windows para habilitar DTC  
  
1. Abra el **Firewall de Windows**:  
  
    **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: pulse la tecla Windows y escriba **Firewall de Windows**. En la ventana Resultados, haga clic en **Firewall de Windows**.  
  
    **Windows 8.1**: pulse la tecla Windows y escriba **Firewall de Windows**. En la ventana Buscar, haga clic en **Configuración**. En la ventana Resultados, haga clic en **Firewall de Windows**.  
  
    **Windows 7 SP1**: haga clic en **Inicio**. En el cuadro de texto **Buscar**, escriba **Firewall de Windows** y haga clic en él para abrirlo.  
  
2. Haga clic en **Configuración avanzada** y, después, en **Reglas de entrada**.  
  
3. En el panel **Reglas de entrada**, haga clic con el botón derecho en **Coordinador de transacciones distribuidas** \* (según corresponda) y, después, haga clic en **Habilitar regla**.  
  
4. Haga clic en **Reglas de salida**.  
  
5. En el panel **Reglas de salida**, haga clic con el botón derecho en **Coordinador de transacciones distribuidas** \* (según corresponda) y, después, haga clic en **Habilitar regla**.  
  
6. En el **Panel de control**, cambie la vista para que se muestre una lista de iconos y, después, haga doble clic en **Herramientas administrativas**.  
  
7. Haga doble clic en **Servicios**.  
  
8. Haga clic con el botón derecho en **Aplicación del sistema COM+**, elija **Reiniciar** y espere hasta que se reinicie el servicio.  
  
9. Haga clic con el botón derecho y reinicie el servicio **Coordinador de transacciones distribuidas**.  
  
10. Haga clic con el botón derecho y reinicie el servicio **SQL Server (MSSQLSERVER)**.  
  
11. Cierre **Servicios (locales)** y, después, cierre **Herramientas administrativas**.  
  
##  <a name="BKMK_SQLAgent"></a> Configurar trabajos del Agente SQL  
  
|            Trabajo            |                                                                                                                                                                                                                                                                                                                     Descripción                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                 Motivos para la configuración                                                                                                                                                                                                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Copia de seguridad de BizTalk Server** |                                     Este trabajo de agente SQL realiza una copia de seguridad de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y de los archivos de registro. Al configurar el trabajo, es necesario determinar parámetros como, por ejemplo, la frecuencia y la ubicación de archivos.<br /><br /> Los vínculos siguientes describen el trabajo de agente SQL y sus parámetros:<br /><br /> [Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)<br /><br /> [Cómo configurar el trabajo de copia de seguridad de BizTalk Server](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)                                      | Este trabajo del agente SQL también trunca los registros de transacción, lo que ayuda a mejorar el rendimiento.<br /><br /> El trabajo **Copia de seguridad de BizTalk Server** no quita ni elimina ningún archivo de copia de seguridad, incluidos los archivos más antiguos. Para eliminar archivos de copia de seguridad, consulte [Se produce un error en el trabajo "Backup BizTalk Server" cuando los archivos de copia de seguridad se acumulan con el tiempo en el servidor de base de datos de Microsoft BizTalk Server](http://support.microsoft.com/kb/982546). |
| **Archivo y purga DTA** | Este trabajo de agente SQL trunca y archiva la base de datos de seguimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (BizTalkDTADb). Al configurar el trabajo, es necesario determinar parámetros como, por ejemplo, el número de días que se deben conservar las instancias completadas o el número de días que se deben conservar todos los datos.<br /><br /> Los vínculos siguientes describen el trabajo de agente SQL y sus parámetros:<br /><br /> [Archivar y purgar la base de datos de seguimiento de BizTalk](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)<br /><br /> [Cómo configurar el trabajo DTA Purge and Archive](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx) |              Este trabajo de agente SQL repercute directamente en el rendimiento, ya que mantiene el host de seguimiento y purga los eventos de seguimiento.<br /><br /> Entre los temas de rendimiento se incluyen:<br /><br /> [Cómo mantener y solucionar problemas de bases de datos de BizTalk Server](http://support.microsoft.com/kb/952555)<br /><br /> [Instrucciones para ajustar el tamaño de la base de datos de seguimiento](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)              |
  
 **Notas**  
  
- Una vez instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se crearán varios trabajos del agente SQL, tal como se describe en los vínculos siguientes:  
  
   [Descripción de los trabajos del agente de SQL en BizTalk Server](http://support.microsoft.com/kb/919776)  
  
   [Estructura de base de datos y trabajos](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)  
  
##  <a name="BKMK_InstallCU"></a> Instalar actualizaciones acumulativas  
 Después de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], instale las actualizaciones acumulativas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que haya disponibles en Windows Update. En el [artículo 2555976 de Knowledge Base](http://support.microsoft.com/kb/2555976) se enumeran los Service Pack y las actualizaciones acumulativas disponibles.  
  
## <a name="next"></a>Siguiente  
[Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[Apéndice C: Archivos CAB redistribuibles](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[Desinstalar y quitar la configuración de BizTalk Server para quitarlo](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)
