---
title: Desinstalar el Acelerador de BizTalk RosettaNet (BTARN) en BizTalk Server | Documentos de Microsoft"
description: Anular la implementación de artefactos y quitar la configuración de BTARN para quitar el Acelerador de BizTalk Server
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 8d289a3705eb0c127dc4d2637c2d6ffd3c122b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209844"
---
# <a name="uninstall-the-rosettanet-accelerator"></a>Desinstale el Acelerador para RosettaNet

## <a name="before-you-begin"></a>Antes de empezar
  
* Si solo ejecuta **Setup.exe**, el proceso de desinstalación no quita los artefactos de supervisión de la actividad económica (BAM), los artefactos de BizTalk, los directorios virtuales de Internet Information Services (IIS) y grupos de aplicaciones.  
  
* Si ha usado la **bucle invertido** utilidad para crear acuerdos espejo para la implementación de un solo equipo, a continuación, ejecutar la herramienta con el **/deshabilitar <** **principal organización**  **>**  opción antes de eliminar los asociados en el **consola de administración de BTARN**.  
  
* Si este servidor forma parte de una implementación de varios equipos, no podrán ejecutarse los **BtarnClean** utilidad o anular la implementación de los ensamblados BTARN manualmente. Quitar los artefactos en un equipo, interrumpe la funcionalidad de los otros equipos.  Si desea desinstalar BTARN en todos los servidores, a continuación, ejecute el **BtarnClean** utilidad. 

  
## <a name="undeploy-the-artifacts"></a>Anular la implementación de los artefactos  

Se recomienda realizar copias de seguridad los artefactos de BAM antes de anular la implementación. 

1. Anular la implementación de todos los artefactos BAM que ha implementado:  
  
    1.  En el símbolo del sistema, ejecute el comando siguiente:  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  En el símbolo del sistema donde se instaló la IU de seguimiento, ejecute el siguiente comando:  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  Para obtener más información acerca de BAM, consulte [administrar Business Activity Monitoring](../../core/managing-bam.md) 
  
2.  Copia de seguridad y eliminar todos los acuerdos, socios y organizaciones internas desde la consola de administración de BTARN. Vea el tema "Administrar la configuración de BTARN" (en el nodo de operaciones de Ayuda de BTARN) para obtener información sobre el uso de la **BtarnConfig** utilidad para hacer copia de seguridad de los acuerdos y socios.  
  
    > [!NOTE]
    >  * Detener y anular la implementación de los artefactos de BizTalk creados por BTARN usando la [BtarnClean](btarnclean.md) utilidad.
    >  * Quitar otros artefactos que ha implementado. Vea [anular la implementación de aplicaciones de BizTalk](../../core/undeploying-biztalk-applications.md) .
  
3.  El programa de instalación de BTARN, busque el Acelerador de BizTalk de carpeta msi\archivos de programa\Microsoft RosettaNet\SDK carpeta. En la carpeta del SDK, haga doble clic en **BTARNClean.exe**y, a continuación, seleccione **Y** para continuar, o **N** para cancelar la ejecución de la utilidad.  
  
    > [!NOTE]
    >  Si el servidor forma parte de un escenario de implementación de varios equipos, puede omitir el paso 3. Anular la implementación de recursos compartidos, interrumpe la funcionalidad de los demás servidores de la implementación.  
  
4.  Anule la implementación de los ensamblados personalizados que haya creado e implementado.  
  
5.  En el símbolo del sistema, vaya a BizTalk Server \Program <your version>\Tracking. Ejecute el siguiente comando: 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a>Quitar la configuración de BTARN
  
1.  Busque y ejecute lo siguiente para quitar la configuración de BTARN:  
  
     ***< unidad\>*****: \Program archivos\\< directorio de instalación\>\Configuration.exe /u**   
  
2.  En el Panel de Control, haga doble clic en **agregar o quitar programas**.  
  
3.  En el **programas actualmente instalados** lista, haga clic en **Acelerador de Microsoft BizTalk para RosettaNet**y, a continuación, haga clic en **cambiar o quitar**.  
  
4.  En el **mantenimiento del programa** cuadro de diálogo, seleccione **quitar**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **resumen** cuadro de diálogo, haga clic en **desinstalar**.  
  
6.  En el **ha completado la desinstalación** cuadro de diálogo, haga clic en **finalizar**.  
  
    > [!NOTE]
    >  El proceso de desinstalación no quita las bases de datos BTARN (BTARNARCHIVE, BTARNCONFIG y BTARNDATA). Debe quitarlas manualmente.  
  
7.  Abra **SQL Server Management Studio**.  
  
8.  En el **conectar al servidor** cuadro de diálogo, haga clic en **conectar**.  
  
9. Expanda el **bases de datos** en el panel izquierdo. Haga clic en uno de las bases de datos BTARN y, a continuación, haga clic en **eliminar**.  
  
10. En el **Eliminar objeto** cuadro de diálogo, seleccione **cerrar conexiones existentes**y, a continuación, haga clic en **Aceptar**.  
  
