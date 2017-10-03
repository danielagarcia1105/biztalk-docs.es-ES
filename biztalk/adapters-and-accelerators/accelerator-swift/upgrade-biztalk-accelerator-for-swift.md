---
title: Actualizar el Acelerador de BizTalk para SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ede2af21-4c7d-4f9e-b255-1ada86eda68d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4e95d248103d99b4b7f50dc925fb220211530f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-biztalk-accelerator-for-swift"></a>Actualizar el Acelerador de BizTalk para SWIFT
Actualizar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)] en BizTalk Server. 

### <a name="before-you-upgrade"></a>Antes de realizar la actualización

* El usuario que ejecuta la actualización debe ser miembro del grupo Administradores de BizTalk Server.
* El servicio de SQL Server (MSSQLSERVER) debe estar ejecutándose cuando se realiza una [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] actualizar.
* No se ejecutan una instalación silenciosa para actualizar a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)].
* Actualización de BizTalk Server y, a continuación, actualizar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)].
* El tiempo de ejecución de BizTalk Server debe estar instalado para el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] actualización para instalar sus componentes en tiempo de ejecución. Si no está instalado el tiempo de ejecución de BizTalk Server anteriores a la [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] actualizar, la [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] componentes no se instalarán y se quitan los ensamblados anteriores desde la caché de ensamblados Global (GAC).
* Al instalar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], se instala el MessagePack. Las versiones existentes de la MessagePack se reemplazan durante la actualización.
* Actualice a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] ejecutando el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] instalación. El programa de instalación migra existente [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] información de configuración. 
* La actualización no puede quitar carpetas y los accesos directos de las características en desuso.

## <a name="supported-upgrade-paths"></a>Rutas de actualización compatibles  
 En la tabla siguiente se enumera los compatibles [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] versiones que se pueden actualizar. "Sí" significa que esa versión se puede actualizar. "No" significa que la versión no se puede actualizar. Si el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] versión no aparece, no se puede actualizar esa versión.  

||[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]|BizTalk Server 2013|
|---|---|---|---|  
|[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2013|Sí|Sí|No|  
|[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2010|No|Sí|Sí|  


## <a name="upgrade-a4swift"></a>Actualización de A4SWIFT

1. Copia de seguridad el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] base de datos y los esquemas de mensajes de SWIFT. Las actualizaciones del programa de instalación el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] base de datos.

2. Copia de seguridad los archivos en el `%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT` y `%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT MessagePack` las carpetas que han actualizado.
  
3. Anular la implementación de los proyectos, los artefactos de BizTalk o ensamblados que hacen referencia a cualquiera de los [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] MessagePack ensamblados.

4. En Visual Studio, manualmente anular la implementación de todos los [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] ensamblados en el orden siguiente:

* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.MrsrService
* Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.

5. Ejecute el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] el programa de instalación para actualizar.

> [!NOTE] 
> Cuando se actualiza [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], la actualización quita los permisos de acceso para la **administradores de A4SWIFT** y **A4SWIFT usuarios** grupos desde el `%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Service` carpeta.         
        
## <a name="post-upgrade-steps"></a>Pasos posteriores a la actualización

1. Usar [BTSTask.exe](../../core/btstask-command-line-reference.md) (%programfiles%\Microsoft BizTalk Server), volver a implementar manualmente los ensamblados de A4SWIFT en el siguiente orden:
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration

    > [!NOTE]
    > No es necesario volver a implementar `Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas`. La instalación vuelve a implementar este ensamblado.

    > [!IMPORTANT] 
    > Antes de volver a generar y volver a implementar el proyecto de esquemas en el paso anterior, elimine las versiones anteriores de `A4SWIFT Base Types.xsd` y `SWIFT Common Data Types.xsd` desde el proyecto de esquema, reemplácelas con las versiones de paquete de mensajes de dichos esquemas y, a continuación, generar e implementar los esquemas proyecto. Si no reemplaza estos esquemas, no podrá generar e implementar el proyecto de esquemas.

2. Volver a compilar e implementar los proyectos o ensamblados que utilizan con versiones anteriores de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] o paquete de mensajes.
3. Si ha realizado algún cambio en los esquemas de paquete de mensajes de SWIFT, realizar los cambios en los nuevos esquemas de paquete de mensajes y, a continuación, genere e implemente esos esquemas.
4. Anular la implementación de las directivas BRE existentes que se instalaron con versiones anteriores de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]. A continuación, instalar e implementar las directivas correspondientes más reciente de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] archivos de instalación. Puede hacerlo manualmente o mediante el **BREDeployment** herramienta.

    > [!NOTE] 
    > Aunque la [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] actualización no producirá los problemas con la funcionalidad del motor de reglas de negocios (BRE), se recomienda que reemplace las versiones anteriores de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] directivas del BRE con las últimas directivas BRE de módulo de mensaje, como algunas directivas del BRE se actualizan para cada paquete de mensajes.
    
5. Si ha personalizado los archivos en el `%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT` carpeta, a continuación, realizar los mismos cambios en las versiones más recientes.
6. Quitar **a4swift_limited** como un miembro del rol db_denydatareader, como se indica a continuación:
    1. Abra SQL Server Management Studio. En Management Studio, expanda **bases de datos**, expanda **Acelerador de BizTalk para SWIFT**y, a continuación, seleccione **Roles**.
    2. Haga doble clic en **a4swift_limited**. Seleccione **permisos**y compruebe Active `Bic11` y `Bic10`. Seleccione **Aceptar**y cierre las propiedades.
    3. Haga doble clic en **db_denydatareader**. En el campo de usuario, seleccione **a4swift_limited**y, a continuación, seleccione **quitar**. Seleccione **Aceptar**.

7. Ejecute el script QFERollUpDBUpdate:

    > [!NOTE]
    > Debe ser un miembro de la **A4Swift administradores** grupo para ejecutar el script QFERollUpDBUpdate.
    
    1. Abra SQL Server Management Studio. En Management Studio, haga clic en nueva consulta. 
    2. Seleccione el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] base de datos de la lista desplegable. 
    3. En el Explorador de Windows, vaya a `%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Scripts`y arrastre la **QFERollUpDBUpdate.sql** de archivos en el panel de consulta nueva y, a continuación, seleccione **Execute**.
    
    
## <a name="upgrading-in-a-multi-server-environment"></a>Realizar una actualización en un entorno de varios servidores

En un servidor de varios [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] entorno, en todos los servidores de actualización de BizTalk Server y, a continuación, actualizar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]. Migre los servidores en este orden:

* Servidor que hospeda el grupo de BizTalk
* Cada nodo de procesamiento
* Servidor del portal de BAM


## <a name="next-steps"></a>Pasos siguientes
[Configurar el Acelerador de BizTalk para SWIFT](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)