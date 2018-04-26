---
title: Requisitos de hardware y Software para BizTalk Server 2016 | Documentos de Microsoft
description: Requisitos previos de software y las listas de versión compatible para instalar BizTalk Server 2016
ms.custom: ''
ms.prod: biztalk-server
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6120afd-310e-4155-8c23-aadb5b9a1a35
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d473d3bf5be874edb430c80032935ddf2c7937bf
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="hardware-and-software-requirements-for-biztalk-server-2016"></a>Requisitos de hardware y software de BizTalk Server 2016

## <a name="hardware-requirements"></a>Requisitos de hardware
En la tabla siguiente se muestran los requisitos mínimos de hardware del equipo de BizTalk Server. Es posible que, en un entorno de producción, el volumen del tráfico imponga requisitos de hardware adicionales para los servidores. 

| Recurso  |Requisito mínimo |
| --- | --- |
|Equipo y procesador | Un equipo con una CPU compatible con Intel Pentium y las siguientes características: <ul><li>Procesadores únicos de 1 GHz o superiores</li><li>Procesadores dobles de 900 MHz o superiores</li><li>Procesadores cuádruples de 700 MHz o superiores</li></ul> **NOTA**: Se admiten procesadores Hyper-Threading y de doble núcleo.<br/><br/>Las versiones de BizTalk Server de 64 bits requieren un sistema operativo de 64 bits que se ejecute en un sistema basado en x64. Los equipos basados en CPU compatibles con la arquitectura de procesador AMD64 (x86-64) y Tecnología de memoria extendida de 64 bits (EM64T) se consideran sistemas basados en x64.<br/><br/>BizTalk Server no es compatible con sistemas basados en Itanium. |
|Memoria | 2 GB o más.|
|Disco duro  |10 GB de espacio en disco duro disponible para una instalación completa, incluido el sistema operativo y todos los requisitos previos de software. El disco duro debe tener el formato NTFS.|

> [!TIP] 
> Los requisitos de hardware enumerados son los mínimos. Cada entorno es diferente y es muy probable que el suyo tenga más requisitos. Consulte [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx) (Recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución de BizTalk Server). 


## <a name="software-requirements--supported-versions"></a>Versiones admitidas y requisitos de software

| Software  |   Versiones |  Se requiere para | 
| --- | --- | --- | 
| Microsoft Windows | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1 </li></ul> | | 
| Servicios de Internet Information Server (IIS)   | La versión que se incluye con el sistema operativo.<br/><br/> En el artículo [KB 224609](https://support.microsoft.com/kb/224609) se enumeran las versiones de IIS. | Proporciona una infraestructura de aplicación web escalable y es necesario para EDI, BAM y el adaptador de SharePoint. |
| Windows Identity Foundation | Se incluye con el sistema operativo como una **característica**. | Opcional. <br/><br/>Lo usa el modelo de objetos del cliente (CSOM) de Windows SharePoint Services, que se instala automáticamente al instalar BizTalk Server. | 
| Microsoft SharePoint  | <ul><li>SharePoint Services 2016</li><li>SharePoint Services 2013 SP1</li><li>SharePoint Services Online</li></ul>  | Opcional. <br/><br/>Si tiene intención de recibir o enviar mensajes desde SharePoint Services, se requiere un equipo con SharePoint Services. Puede instalarse en el mismo equipo que BizTalk Server o, preferiblemente, en un equipo distinto. |
| Microsoft Office  | <ul><li>Microsoft Office Excel 2016</li><li>Microsoft Office Excel 2013</li></ul>**NOTA**: BizTalk Server solo admite versiones de 32 bits de Office.  | Opcional. <br/><br/>Supervisión de la actividad económica (BAM) lo requiere para mostrar una visualización en tiempo real de los procesos empresariales. | 
| Microsoft .NET Framework  | <ul><li>.NET framework 4.7 (a partir de [CU2](https://support.microsoft.com/kb/4021095))</li><li>.NET Framework 4.6.*x* </li></ul>**Tenga en cuenta**: proyectos de BizTalk creados en Visual Studio requieren el establecimiento de destino de compilación de Visual Studio a la versión de .NET Framework. | Se requiere para todos los componentes administrados de BizTalk Server. | 
| Microsoft Visual Studio |Visual Studio 2015 | Opcional. <br/><br/>Proporciona un entorno de desarrollo para crear aplicaciones de BizTalk Server. Se recomienda la versión Ultimate Edition, pero las versiones Premium y Professional también son compatibles. Se requiere para el SDK y las herramientas de desarrollo de BizTalk Server. |
| Paquete redistribuible de Microsoft Visual C++ 2013 | Se requieren las versiones x86 y x64. Descárguela en [Paquetes redistribuibles de Visual C++ para Visual Studio 2013](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package).    | Requerido.<br/><br/>El paquete redistribuible de Microsoft Visual C++ instala componentes en tiempo de ejecución de las bibliotecas de Visual C++ que son necesarios para ejecutar aplicaciones desarrolladas con Visual C++ en un equipo que no tiene instalado Visual C++.<br/><br/>**Nota**: <br/> Se requiere la versión de 2013, aunque se use Visual Studio 2015.|
| Microsoft SQL Server  | <ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul> | Se requiere para tiempo de ejecución de BizTalk Server, EDI y BAM. <br/><br/>Para obtener un rendimiento óptimo, Microsoft recomienda usar la versión Enterprise Edition de SQL Server. Para poder usar el SDK de BizTalk Server en su totalidad o implementar aplicaciones de BizTalk Server desde Visual Studio, instale las herramientas de desarrollo de SQL Server. <br/><br/>Otras consideraciones: <ul><li>Para usar Grupos de disponibilidad (GD) AlwaysOn de SQL Server, utilice SQL Server 2016 y versiones más recientes. Solo los GD AlwaysOn de SQL Server 2016 admiten MSDTC; BizTalk requiere MSDTC. </li><li>No se admite la agregación en tiempo real (ATR) de BAM en la versión Standard Edition de SQL Server. Para usar ATR de BAM, instale SQL Server Enterprise Edition.</li><li>No se recomienda usar SQL Server Express Edition. Esta edición no incluye ciertas características que necesita BizTalk Server.</li><li>BizTalk Server admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias. No se admiten intercalaciones binarias.</li></ul> |  |
| Correo electrónico de base de datos de SQL Server  | La versión que se incluye con SQL Server. [Configure el Correo electrónico de base de datos de SQL Server](https://msdn.microsoft.com/library/hh245116(v=sql.130).aspx).| Opcional. <br/><br/>Necesario para usar las alertas de BAM. | 
| SQL XML | SQL XML 4.0 con Service Pack 1. [Descargue SqlXml 4.0 Service Pack 1 (SP1)](https://www.microsoft.com/en-us/download/details.aspx?id=30403). | Se requiere para el tiempo de ejecución de BizTalk Server, herramientas administrativas y BAM. <br/><br/> SQLXML proporciona compatibilidad entre XML y la base de datos de SQL Server. Permite a los programadores tender un puente entre los datos XML y los datos relacionales. Puede crear una vista XML de los datos relacionales existentes y trabajar con la vista como si se tratara de un archivo XML. <br/><br/>**Nota**: <br/>el archivo CAB redistribuible lo instala automáticamente. SQL XML puede tener sus propios requisitos de software (como `.NET Framework 3.5` y `.NET Framework 2.0`), que no se incluyen en el archivo CAB. Si BizTalk Server tiene acceso a Internet, los requisitos de software de SQL XML podrían instalarse automáticamente. Si BizTalk Server no tiene acceso a Internet, debe instalar manualmente los requisitos de software de SQL XML.| 
| WinSCP | WinSCP versión 5.7.7. [Descargue WinSCP](http://winscp.net).| Necesario para usar el adaptador SFTP. |
| Adaptador de MQSeries | <ul><li>IBM WebSphere MQ 8</li><li>IBM WebSphere MQ 9 (a partir de BizTalk 2016 CU4)</li></ul> | Opcional.<br/>Solo es necesario si mediante IBM WebSphere MQ. |
|Sistemas LOB y enterprise | [Línea de negocio (LOB) y los sistemas empresariales compatibles](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) enumera las versiones compatibles. | Necesarias para usar los adaptadores de BizTalk Adapter Pack. <br/><br/> [BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md) enumera los adaptadores disponibles del sistema. |

## <a name="service-pack-and-cumulative-update-support"></a>Compatibilidad con Service Packs y actualizaciones acumulativas

Se admiten todos los service packs, actualizaciones acumulativas, actualizaciones de seguridad y revisiones en un servidor BizTalk Server. Se recomienda encarecidamente instalar la última actualización de Windows, SQL Server, Visual Studio y de cualquier otro programa instalado. Para los Service Packs de productos de Microsoft, se ofrece soporte técnico en función del soporte técnico básico para ese producto. Consulte el [índice del ciclo de vida de soporte técnico](http://go.microsoft.com/fwlink/p/?LinkID=151890) de BizTalk Server, SQL Server, Visual Studio y otros programas de Microsoft.

[Service Pack y lista de actualizaciones acumulativas para BizTalk Server](https://support.microsoft.com/help/2555976)

 ## <a name="next-step"></a>Paso siguiente
 
 [Requisitos previos de configuración e instalación](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)
