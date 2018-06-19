---
title: Importar o exportar el panel de configuración de uso de configuración de BizTalk | Documentos de Microsoft
description: Usar administración de BizTalk Server para importar o exportar la configuración entre entornos de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc2f0b44-d79b-4f95-811a-0843e3d6d1c8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e33b8659701ab991f7b7467c8ab3edd8b79def4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255140"
---
# <a name="use-settings-dashboard-to-import-or-export-biztalk-settings"></a>Utilice el panel de configuraciones para importar o exportar la configuración de BizTalk 

## <a name="overview"></a>Información general
Mediante el Panel de valores de configuración de BizTalk, puede exportar la configuración de un entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e importarla a otro entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], lo que permitirá reducir el tiempo para solución global. Esto es especialmente práctico en aquellas situaciones en las que los administradores intentan mejorar el rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de ensayo y, una vez obtenidos los resultados deseados, pueden importar la configuración en un entorno de producción. Este tema proporciona el procedimiento detallado para importar la configuración de grupo, host e instancia de host de BizTalk, mediante el panel de valores de configuración.  

> [!TIP]
> También se puede utilizar la utilidad de línea de comandos BTSTask para importar o exportar la configuración de grupo, Host e instancia de Host. Vea [importación o exportación BTSTask de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-btstask.md).

  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe iniciar sesión como miembro del grupo Administradores de BizTalk Server.  
  
## <a name="import-the-biztalk-group-host-and-host-instance-settings"></a>Importar el grupo de BizTalk, el host y la configuración de la instancia de host  

> [!IMPORTANT]
>  Para importar la configuración de BizTalk Server de un entorno determinado, debe haber guardado esta configuración y haberla exportado a un archivo XML. **Exportar la configuración de BizTalk** (en este tema) o [importación o exportación BTSTask de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-btstask.md) puede ayudar a.
  
 Al importar el archivo XML, se puede replicar la configuración de BizTalk Server necesaria en el equipo de destino. Con el panel de valores de configuración, puede importar la configuración de grupo, host e instancia de host y asignar las propiedades entre sí. Las hipótesis necesarias para importar la configuración son:  
  
-   La topología de BizTalk Server es coherente del entorno de origen al entorno de destino.  
  
-   Se pueden asignar las definiciones de host entre los entornos de origen y destino. Debe poder asignar todos los hosts del entorno de origen a los del entorno de destino.  
  
-   El entorno de destino tiene un hardware similar (si no idéntico) al entorno de origen. Esto es esencial, ya que algunas de las configuraciones dependen del hardware subyacente.  

### <a name="import-steps"></a>Pasos de la importación
  
1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo, haga clic en **importación**. El **Asistente para importar configuración** aparece el cuadro de diálogo.  
  
    > [!NOTE]
    >  El **grupo de destino** muestra la información de la máquina de destino donde van a importar la configuración de grupo.  
  
     ![Especifique la ubicación del archivo para importar la configuración de](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")  
  
3.  Haga clic en el **especificar la ubicación del archivo** página y, a continuación, haga clic en ![examinar el archivo de configuración](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse"). Aparece el explorador de archivos.  
  
4.  Seleccione el archivo XML que contiene la configuración del entorno de origen y, a continuación, haga clic en **abiertos**. El **ubicación del archivo** muestra la ruta de acceso del archivo XML y el **grupo origen** se rellena con la información del grupo de la máquina de origen. Haga clic en **Siguiente**.  
  
5.  En el **asignación de Host** página, realice lo siguiente:  
  
    1.  Desde el **Hosts de destino** , seleccione un host de destino para el que desea especificar el host de origen y, a continuación, haga clic en **agregar**.  
  
         ![Asignación de host](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")  
  
    2.  En el **Seleccionar entidad de origen** cuadro de diálogo, seleccione el host de origen y, a continuación, haga clic en **Aceptar**.  
  
        > [!NOTE]
        >  Para asignar varios hosts de destino a un único host de origen, repita los pasos **5a** y **5b**.  
  
    3.  En el **asignación de Host** página, haga clic en **siguiente**.  
  
6.  En el **asignación de la instancia de Host** página, realice lo siguiente:  
  
    1.  En la lista de instancias de host de destino, seleccione una instancia de host de destino para el que desea especificar la instancia de host de origen y, a continuación, haga clic en **agregar**.  
  
        > [!NOTE]
        >  Las instancias de host solo se pueden asignar en el host correspondiente creado en la Asignación de host. Por ejemplo, si especifica una asignación donde **SourceHost1** se asigna a **DestinationHost1**, a continuación, las instancias de **DestinationHost1** solo se pueden asignar a las instancias de de **SourceHost1**.  
        >   
        >  El Asistente para importar administra la restricción anterior. Debe seguir esta restricción ya que, en caso contrario, las tareas de BizTalk lanzarán errores.  
        >   
        >  Debe usar la convención **nombrehost: NombreEquipo** para especificar una instancia de host en un archivo de asignación. Por ejemplo, **host1: Server1** en una asignación de archivo indica que la instancia de **Host1** está en ejecución o disponible en **Server1**.  
  
         ![Asignación de la instancia de host](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")  
  
    2.  En el **Seleccionar entidad de origen** cuadro de diálogo, seleccione la instancia de host de origen y, a continuación, haga clic en **Aceptar**.  
  
        > [!NOTE]
        >  Para asignar varias instancias de host de destino a una instancia de host de origen único, repita los pasos **6a** a **6b**.  
  
    3.  En el **asignación de la instancia de Host** , haga clic en **siguiente**.  
  
7.  En el **resumen de importación** cuadro de diálogo, compruebe si todas las configuraciones de importación para los entornos de origen y destino que creó están como desea y, a continuación, haga clic en **importar**. El **progreso** página muestra el progreso de la importación de la configuración.  
  
    > [!WARNING]
    >  No puede deshacer la importación de la configuración de BizTalk Server. Si hace clic en **importación**, se inicia el proceso para importar la configuración del entorno de origen al entorno de destino y **cancelar** está deshabilitado. Asegúrese de que desea continuar con la importación antes de hacer clic **importar**.  
  
8.  En el **importar resultados** ficha, comprobar el estado de importación de la configuración de grupo, Host e instancia de Host y, a continuación, haga clic en **finalizar** para completar la operación de importación. Toda la configuración del entorno de origen importada se aplica al entorno de destino.  
  
     ![Importar resultados](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")  

## <a name="export-the-biztalk-group-host-and-host-instance-settings"></a>Exportar el grupo de BizTalk, el host y la configuración de la instancia de host  

1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo, haga clic en **exportar**. Aparece el cuadro de diálogo **Guardar como** .  
  
3.  Desplácese hasta la ubicación en que desea guardar la configuración de BizTalk actual. Escriba el nombre de archivo, seleccione el tipo de formato XML y, a continuación, haga clic en **guardar**.  

> [!IMPORTANT]
>  No no se recomienda actualizar manualmente el archivo XML exportado. Al importar un archivo XML actualizado a un entorno de producción, el proceso de importación puede producir un error debido a algún error de coincidencia de tipo de datos u otros errores introducidos por la edición manual.  

## <a name="see-also"></a>Vea también  
 [Mediante el panel de configuración de BizTalk Server ajuste del rendimiento](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)