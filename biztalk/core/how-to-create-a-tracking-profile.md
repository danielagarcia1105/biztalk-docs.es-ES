---
title: Cómo crear un perfil de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 676ae7e8-f3eb-45f1-ad2e-807b434c0bf9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f5d6cbb210cb292cd8ae7d0e2f4ff811984377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248940"
---
# <a name="how-to-create-a-tracking-profile"></a>Cómo crear un perfil de seguimiento
Se crean perfiles de seguimiento para vincular definiciones de actividad de BAM a ensamblados implementados y propiedades de mensajería de BizTalk Server. Al abrir el Editor de perfiles de seguimiento, puede crear un perfil de seguimiento nuevo al hacer clic en el vínculo de actividad de importación o en el elemento de menú de importación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
-   Una base de datos existente de administración de BizTalk de la que tiene permisos.  
  
-   El TPE configurado para utilizar la base de datos de administración de BizTalk.  
  
-   Una definición de actividad de BAM existente en la base de datos de importación principal de BAM.  
  
### <a name="to-create-a-tracking-profile"></a>Para crear un perfil de seguimiento  
  
1.  En el equipo o equipos que se han identificado como el sistema de origen, abra la **Editor de perfiles de seguimiento**. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **BTSTrkEditor.exe**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En medio del panel izquierdo del TPE, haga clic en **haga clic aquí para seleccionar una definición de actividad de BAM** vínculo. Se abrirá la **Importar definición de actividad de BAM** cuadro de diálogo.  
  
3.  Desde el **nombre de definición de actividad de BAM** cuadro de lista Seleccione la actividad en el que se va a basar el seguimiento. Si la lista contiene muchas actividades implementadas, puede escribir parte del nombre de la actividad en el **en cadena** cuadro de texto y haga clic en el **búsqueda** botón. Esto limita la lista de actividades que se muestra para los nombres que contienen el nombre parcial que ha escrito.  
  
4.  Una vez que haya seleccionado la actividad, haga clic en el **Aceptar** botón. Se abrirá un perfil de seguimiento nuevo basado en la actividad seleccionada y muestra el perfil en el panel izquierdo del TPE.  
  
## <a name="see-also"></a>Vea también  
 [Creación de perfiles de seguimiento](../core/creating-tracking-profiles.md)