---
title: Operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4006bbe-91ca-4cd9-844d-5ed63142001f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dab9b8d008b9bb36fa5a09789b531ea9fbee113
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006429"
---
# <a name="operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter"></a>Operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL
Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar operaciones en tablas o vistas que tienen columnas de tipos definidos por el usuario (UDT). Puede usar las operaciones de tabla estándar (Insert, Update, Delete y Select) para leer o escribir datos en columnas de tipos UDT. También puede ejecutar procedimientos almacenados y funciones en dichas tablas. Sin embargo, deberá realizar determinadas tareas antes de poder usar el adaptador para operar en tablas con columnas UDT. Una vez que haya realizado estas tareas, puede usar el adaptador:  

-   Realizar la inserción, eliminación, actualización y las operaciones Select, como se describe en [Insert, update, delete o selectas operaciones mediante BizTalk Server con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md).  

-   Ejecutar procedimientos almacenados, como se describe en [ejecutar procedimientos almacenados en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).  

-   Realizar operaciones compuestas en tablas con columnas UDT, como se describe en [ejecutar operaciones compuestas en SQL Server con BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  

-   Sondear las tablas con columnas UDT, como se describe en [basado en sondeo de recibir mensajes de cambio de datos desde SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md).  

-   Realizar otras operaciones, como se describe en [desarrollar las aplicaciones de BizTalk](../../core/develop-your-biztalk-applications.md).  

## <a name="considerations-while-performing-operations-on-tables-with-udts"></a>Consideraciones al realizar operaciones en tablas con UDT  
 Debe realizar las tareas siguientes antes de poder usar el adaptador para realizar operaciones en tablas con columnas UDT.  

- **Al generar el esquema para el uso de la operación [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  


  |                       Tipo UDT                        |                                                                                                                                                                        Ubicación de los ensamblados                                                                                                                                                                        |
  |-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | Los UDT incluyen con SQL Server, por ejemplo, Geography  | -Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.<br />-Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.<br /><br /> Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente. |
  | UDT, pero no se incluye con SQL Server definido por los usuarios |                      Asegúrese de que los ensamblados respectivos para los UDT están disponibles en la misma ubicación que el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] ejecutable devenv.exe. El archivo ejecutable es suele estar disponible en `<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`.                      |


- **Mientras se realiza la operación con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]**  


  |                       Tipo UDT                        |                                                                                                                                                                        Ubicación de los ensamblados                                                                                                                                                                        |
  |-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | Los UDT incluyen con SQL Server, por ejemplo, Geography  | -Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.<br />-Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.<br /><br /> Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente. |
  | UDT, pero no se incluye con SQL Server definido por los usuarios |                                     Asegúrese de que los ensamblados respectivos para los UDT están disponibles en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ubicación de instalación. Para que BizTalk Server, esto suele \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.                                      |


- **Mientras se realiza la operación con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  

  |Tipo UDT|Ubicación de los ensamblados|  
  |--------------|----------------------------|  
  |Los UDT incluyen con SQL Server, por ejemplo, Geography|-Asegúrese de que Microsoft.SqlServer.Types.dll se agrega a la GAC.<br />-Asegúrese de que SqlServerSpatial.dll está disponible en la carpeta System32.<br /><br /> Puede instalar estos archivos DLL en el equipo ejecutando el programa de instalación de SQL Server y seleccionando **herramientas de administración – básica** y **herramientas de administración – completa** en la **selección de características**página del asistente.|  
  |UDT, pero no se incluye con SQL Server definido por los usuarios|Asegúrese de que los ensamblados respectivos para los UDT están disponibles en la misma ubicación que el archivo ejecutable del proyecto, que normalmente se encuentra en la carpeta \bin\Debug del proyecto.|  

  Cuando haya completado estas tareas, están establecidos para realizar operaciones en tablas con UDT.  

## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)