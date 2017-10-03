---
title: Requisitos de hardware y Software para BizTalk Server 2013 y 2013 R2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b15dd23c-c899-43fb-b2da-f8ac55c055bf
caps.latest.revision: "34"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5202c6777b4296141bc74823834d54b97b7f1572
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2"></a>Requisitos de hardware y software de BizTalk Server 2013 y 2013 R2
En este tema se enumeran los requisitos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 y [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)].  
  
##  <a name="BKMK_HardRequirements"></a> Requisitos de hardware  
 En la tabla siguiente se muestran los requisitos mínimos de hardware del equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Es posible que, en un entorno de producción, el volumen del tráfico determine requisitos de hardware adicionales para los servidores.  
  
|Componente|Requisito mínimo|  
|---------------|-------------------------|  
|Equipo y procesador|Un equipo con una CPU compatible con Intel Pentium y las siguientes características:<br /><br /> - Procesadores únicos de 1 GHz o superiores<br />- Procesadores dobles de 900 MHz o superiores<br />- Procesadores cuádruples de 700 MHz o superiores<br /><br /> Se admiten procesadores Hyper-Threading y de doble núcleo.<br /><br /> Las versiones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de 64 bits requieren un sistema operativo de 64 bits que se ejecute en un sistema basado en x64. Los equipos basados en CPU compatibles con la arquitectura de procesador AMD64 (x86-64) y Tecnología de memoria extendida de 64 bits (EM64T) se consideran sistemas basados en x64.<br /><br /> Los sistemas basados en Itanium no admiten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|Memoria|2 GB de RAM|  
|Disco duro|10 GB de espacio en disco duro disponible para una instalación completa, incluido el sistema operativo y todos los requisitos previos de software. El disco duro debe tener el formato NTFS.|  
|Unidad|Unidad de CD-ROM o DVD-ROM (compartida o adjunta)|  
  
 **Aportación de la comunidad**: [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx) (Recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución de BizTalk Server).  
  
##  <a name="BKMK_SoftRequirements"></a> Requisitos de software  
 En esta tabla se enumera el software mínimo necesario para ejecutar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Se le guiará a través de los pasos de instalación para todos estos requisitos previos en una sección posterior.  
  
|Software|[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013|Se requiere para|  
|---|---|---|---|  
|**Microsoft Windows**|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1|Windows Server 2012<br/>Windows Server 2008 R2 SP1<br/>Windows 7 SP1<br/>Windows 8||  
|**Internet Information Services (IIS)**|La versión que se incluye con el sistema operativo. En el artículo KB [224609](http://support.microsoft.com/kb/224609) se enumeran las versiones.|La versión que se incluye con el sistema operativo. En el artículo KB [224609](http://support.microsoft.com/kb/224609) se enumeran las versiones.|Proporciona una infraestructura de aplicación web escalable y es necesario para EDI, BAM, adaptador de WSS y UDDI.|  
|**Windows Identity Foundation**|Es necesario cuando se usa el Modelo de objetos del lado cliente (CSOM) de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)].<br /><br /> En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se enumeran las opciones específicas del adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|Es necesario cuando se usa el Modelo de objetos del lado cliente (CSOM) de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)].<br /><br /> En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se enumeran las opciones específicas del adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|El adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] o [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Online, si se usa con el modelo de objeto de cliente (CSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. WIF no es necesario cuando se usa el Servicio web de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], que dejó de usarse en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013.<br /><br /> En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se proporciona información específica sobre las opciones de instalación del adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].|  
|**Microsoft SharePoint**|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013 SP1<br/>[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Online<br/>[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010<br /><br /> En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se enumeran las opciones específicas del adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013<br/>[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Online<br/>[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010<br/>[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2007<br /><br /> En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se enumeran las opciones específicas del adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|Si recibe o envía mensajes desde [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], necesita un equipo con [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. SharePoint puede instalarse en el mismo equipo que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o, preferiblemente, en otro distinto.<br /><br /> En [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) se enumeran las opciones específicas del adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|**Microsoft Office**|Microsoft Office Excel 2013<br/>Microsoft Office Excel 2010<br /><br /> Si usa Excel 2010, instale [KB 2345338](http://support.microsoft.com/kb/2345338). <br /><br />**Nota**  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo es compatible con la versión de 32 bits de Microsoft Office.|Microsoft Office Excel 2013<br/>Microsoft Office Excel 2010<br /><br /> Si usa Excel 2010, instale [KB 2345338](http://support.microsoft.com/kb/2345338). <br /><br />**Nota**  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo es compatible con la versión de 32 bits de Microsoft Office.|Supervisión de la actividad económica (BAM) lo requiere para mostrar una visualización en tiempo real de los procesos empresariales. Si no usa BAM, no es necesario Microsoft Office.|  
|**Microsoft .NET Framework**|<ul><li>[!INCLUDE[dotnet45](../includes/dotnet45-md.md)].x</li><li>[!INCLUDE[btsDotNetFramework_md](../includes/btsdotnetframework-md.md)] 4.6.x</li></ul>**Nota**  Los proyectos de BizTalk creados en Visual Studio requieren que el destino de compilación de Visual Studio se establezca en .NET Framework 4.5.|[!INCLUDE[dotnet45](../includes/dotnet45-md.md)].x <br/><br/>**Nota**  Los proyectos de BizTalk creados en Visual Studio requieren que el destino de compilación de Visual Studio se establezca en .NET Framework 4.5.|Todos los componentes administrados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lo necesitan.|  
|**Microsoft Visual Studio**|Visual Studio 2013 <br /><br />**Nota**  Si tiene instalado Visual Studio 2013 Update 2, es posible que eche en falta algunos artefactos al crear un nuevo proyecto de BizTalk Server en Visual Studio. Para solucionar este problema, debe instalar [Visual Studio 2013 Update 3](http://go.microsoft.com/fwlink/p/?LinkId=403949).|Visual Studio 2012|Proporciona un entorno de desarrollo para crear aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Se recomienda la versión Ultimate Edition, pero las versiones Premium y Professional también son compatibles.   Se requiere para el SDK y las herramientas de programadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|**Paquete redistribuible de Microsoft Visual C++ 2010**|En un equipo basado en x86, instale solo la versión x86 del paquete. En un equipo basado en x64, instale las versiones x86 y x64 del paquete. El instalador está disponible en la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en \Platform\SSO\Platform.|En un equipo basado en x86, instale solo la versión x86 del paquete. En un equipo basado en x64, instale las versiones x86 y x64 del paquete. El instalador está disponible en la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en \Platform\SSO\Platform.||  
|**Microsoft SQL Server**|[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]<br/>[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] SP1<br /><br /> Para obtener un rendimiento óptimo, Microsoft recomienda usar la versión Enterprise Edition de SQL Server. Para poder usar el SDK de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en su totalidad o implementar aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde Visual Studio, instale las herramientas de desarrollo de SQL Server. <br /><br />**Importante**  <ul><li>No se admite la agregación en tiempo real (ATR) de BAM en la versión Standard Edition de SQL Server. Para usar ATR de BAM, debe instalar SQL Server Enterprise Edition.</li><li>No se recomienda utilizar SQL Server Express Edition en un entorno de producción. Express Edition no incluye ciertas características que necesita [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</li><li>[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias. No se admiten intercalaciones binarias.</li></ul>|[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]<br/>[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] SP1<br /><br /> Para obtener un rendimiento óptimo, Microsoft recomienda usar la versión Enterprise Edition de SQL Server. Para poder usar el SDK de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en su totalidad o implementar aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde Visual Studio, instale las herramientas de desarrollo de SQL Server. <br /><br />**Importante**  <ul><li>No se admite la agregación en tiempo real (ATR) de BAM en la versión Standard Edition de SQL Server. Para usar ATR de BAM, debe instalar SQL Server Enterprise Edition.</li><li>No se recomienda utilizar SQL Server Express Edition en un entorno de producción. Express Edition no incluye ciertas características que necesita [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</li><li>[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias. No se admiten intercalaciones binarias.</li></ul>|Se requiere para el runtime de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], EDI y BAM.|  
|**Correo electrónico de base de datos de SQL Server** / **SQL Server 2005 Notification Services**|Configure el [Correo electrónico de base de datos de SQL Server](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).|Si usa [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], debe instalar SQL Server 2005 Notification Services. Notification Services no se incluye con [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]. Descargue SQL Server 2005 Notification Services del [Feature Pack de Microsoft SQL Server 2005 de diciembre de 2008](http://go.microsoft.com/fwlink/p/?LinkId=154501).<br /><br /> Si usa [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], configure el [Correo electrónico de base de datos de SQL Server](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).|Lo usan las alertas de BAM. <br /><br />**Nota**  Solo es necesario si se usan las alertas de BAM.|  
|**SQLXML 4.0 con Service Pack 1**|Para instalar SQLXML 4.0 SP1, consulte [SqlXml 4.0 Service Pack 1 (SP1)](http://www.microsoft.com/download/details.aspx?id=30403).|Para instalar SQLXML 4.0 SP1, consulte [Microsoft SQL Server 2008 Feature Pack](http://go.microsoft.com/fwlink/?LinkID=189325) (http://go.microsoft.com/fwlink/p/?LinkID=189325).|Es necesario para el runtime de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las herramientas administrativas y BAM. Permite la compatibilidad XML para su base de datos de SQL Server y permite a los programadores cubrir el hueco entre XML y los datos relacionales. Hace posible crear una vista XML de los datos relacionales existentes y trabajar con ellos como si se tratara de archivos XML.|  
  
##  <a name="BKMK_SPCUSupport"></a> Compatibilidad con Service Packs y actualizaciones acumulativas  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite todos los Service Packs, actualizaciones acumulativas, actualizaciones de seguridad y revisiones. Se recomienda encarecidamente instalar la última actualización de [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)], [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], Visual Studio y de cualquier otro programa instalado. Para los Service Packs de productos de Microsoft, se ofrece soporte técnico en función del soporte técnico básico para ese producto. Consulte el [índice del ciclo de vida de soporte técnico](http://go.microsoft.com/fwlink/p/?LinkID=151890) de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], Visual Studio y otros programas de Microsoft.  
  
## <a name="next"></a>Siguiente  
 [Consideraciones previas a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/c39de794-fd80-422b-9171-3e3c418aa691)  
  
## <a name="see-also"></a>Ver también  
 [Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md)   
 [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [Apéndice C: Archivos CAB redistribuibles](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md)