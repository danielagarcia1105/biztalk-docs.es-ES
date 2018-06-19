---
title: Problemas conocidos de instalación, configuración e implementación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda1bd5c8167bbf9f6049b3620c0c949950b1e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299836"
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a>Problemas conocidos en la instalación, configuración e implementación
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a>Algunos artefactos de EDI y AS2 de BizTalk siguen activos después de quitar la configuración  
  
##### <a name="problem"></a>Problema  
 Tras quitar la configuración de la característica EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], algunos artefactos de BizTalk Server relacionados con el procesamiento de EDI y AS2 seguirán activos en el contexto de la configuración de grupos de BizTalk. Estos artefactos incluirán las canalizaciones EDI y AS2 y la orquestación de procesamiento por lotes. Como resultado, seguirá pudiendo realizar un procesamiento básico de EDI y AS2 incluso después de haber quitado la configuración de la característica de EDI y AS2 de BizTalk.  
  
##### <a name="cause"></a>Causa  
 Hay puertos activos asociados con el procesamiento de EDI y AS2. Algunos artefactos seguirán funcionando mientras estos puertos permanezcan activos.  
  
##### <a name="resolution"></a>Solución  
 Para deshabilitar todos los artefactos de EDI o AS2, debe deshabilitar, detener o eliminar los puertos asociados con el procesamiento de EDI y AS2.  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a>Si se cambia el nombre del equipo de BizTalk Server o del equipo de SQL Server después de configurar BizTalk Server, el Asistente para configuración dará errores  
  
##### <a name="problem"></a>Problema  
 Este problema puede manifestarse de varias maneras:  
  
-   La configuración de BizTalk Server cargará la página Información general de forma correcta aunque al tratar de configurar una característica, las opciones de ésta no aparecerán en pantalla.  
  
-   El asistente para configuración no se puede conectar al servidor SQL Server.  
  
-   El intento de anular la configuración de todo conseguirá anular la configuración de algunas características pero no de todas.  
  
##### <a name="cause"></a>Causa  
 La configuración de BizTalk Server almacena el nombre de red del equipo. Cuando se cambia el nombre del equipo, el asistente para configuración y la configuración de BizTalk Server no pueden encontrar el servidor de BizTalk Server. Se produce un problema parecido si se cambia el nombre del equipo del servidor SQL Server una vez que se haya configurado BizTalk Server.  
  
##### <a name="resolution"></a>Solución  
 No cambie el nombre del equipo del servidor BizTalk Server o del servidor SQL Server. Si es necesario cambiar el nombre de un servidor, anule previamente la configuración de todas las características de BizTalk. Una vez que haya cambiado el nombre del equipo, vuelva a configurar las características de BizTalk Server.  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a>Se produce un error en el Asistente para configuración de reglas de negocios de BizTalk Server  
  
### <a name="problem"></a>Problema  
  
-   El Asistente para configuración de reglas de negocio falla con el error "Error al configurar algunos componentes. No se aplicó la configuración a esos componentes".  
  
-   En los equipos de BizTalk Server para los que ya se ha configurado correctamente el motor de reglas de negocio, se produce un error al iniciar el servicio Actualización del motor de reglas y no se puede iniciar manualmente.  
  
 Cuando se da este problema, es posible que se genere un error similar al siguiente en el registro de aplicación del equipo de BizTalk Server:  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a>Causa  
 El Centro de protección contra malware de Microsoft lanzó un archivo de firma actualizado, para tratar una posible amenaza de SettingsModifier:Win32/PossibleHostsFileHijack. Este archivo de firma actualizado puede causar que el software de detección de malware de Microsoft, tal como Windows Defender, actualice el archivo HOSTS local para mitigar las amenazas de SettingsModifier:Win32/PossibleHostsFileHijack. Como resultado de estos cambios, es posible que se produzca un error al iniciar el Servicio de actualización del motor de reglas de BizTalk Server.  
  
### <a name="resolution"></a>Solución  
 Actualice el archivo HOSTS local para que incluya la línea siguiente:  
  
```  
127.0.0.1         localhost  
```  
  
 El archivo HOSTS se encuentra en el directorio %systemroot%\drivers\etc\.  
  
> [!NOTE]
>  Para obtener más información sobre la actualización de firma del Centro de protección contra malware de Microsoft que trata una posible amenaza de SettingsModifier:Win32/PossibleHostsFileHijack, consulte [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221).  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a>Se produce un error al dar de alta una orquestación si en la base de datos de GAC/Mgmt faltan ensamblados a los que se hace referencia  
  
##### <a name="problem"></a>Problema  
 Se produce un error al dar de alta una orquestación si en la base de datos de GAC/Mgmt faltan referencias (ensamblados de C# a los que se hace referencia en las orquestaciones). Durante la reimplementación, puede ser necesario dar de alta la orquestación basándose en su estado existente. Si faltan referencias, también se produce un error en la implementación.  
  
##### <a name="cause"></a>Causa  
 En la base de datos de GAC/Mgmt faltan ensamblados a los que se hace referencia.  
  
##### <a name="resolution"></a>Solución  
 Agregue los ensamblados a los que se hace referencia en la GAC, o agréguelos como recursos, para que se almacenen en la base de datos Mgmt y estén disponibles al dar de alta la orquestación.  

## <a name="community-blog-biztalk-2013-r2-bugs-issues--quirks"></a>Blog de la comunidad: errores, problemas y peculiaridades de BizTalk 2013 R2

[BizTalk Server 2013 R2 known bugs, issues, quirks](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/) (Errores, problemas y peculiaridades conocidos de BizTalk Server 2013 R2)
  
## <a name="additional-configuration-topics"></a>Temas adicionales sobre configuración  
  
 [Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)  
  
 [Configurar BizTalk Server en una máquina virtual de Azure](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [Configuración de BizTalk Server en un clúster](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [Proteger la implementación de BizTalk Server](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  