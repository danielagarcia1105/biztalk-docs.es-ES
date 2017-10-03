---
title: "Solución de problemas de herramientas de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7aedd8977042d15176781b0595bd5bb225a2fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-tools"></a>Herramientas de solución de problemas de BizTalk Server
En este tema se proporciona una ubicación centralizada de información sobre problemas comunes que se pueden producir al usar las herramientas incluidas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="known-issues"></a>Problemas conocidos  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a>Es posible que las herramientas y utilidades de BizTalk Server no funcionen correctamente en un sistema Windows compatible con UAC  
 **Problema**  
  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se instala en un sistema compatible con el control de cuentas de usuario (UAC), es posible que las herramientas incluidas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se inicien o no funcionen correctamente.  
  
 **Causa**  
  
 Al ejecutar una aplicación clasificada para un nivel de privilegios específico, si el nivel requerido es mayor que el del usuario que ejecuta la aplicación, UAC mostrará un mensaje que permite elevar temporalmente el privilegio de la aplicación al nivel necesario. Las herramientas suministradas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tienen las clasificaciones correctas habilitadas para solicitar automáticamente la elevación de privilegios, por lo que la herramienta intentará ejecutarse en el nivel de privilegios actual del usuario que ejecuta la aplicación y se producirá un error si se requiere un nivel de privilegios mayor.  
  
 **Resolución**  
  
 Para resolver este problema, ejecute todas las herramientas de BizTalk Server con privilegios de administrador. Para ejecutar una herramienta con privilegios de administrador, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
 Para obtener más información sobre el Control de cuentas de usuario, consulte [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167).  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a>A veces, el cuadro de herramientas del Asignador de BizTalk puede aparecer vacío  
 **Problema**  
  
 A veces, al abrir el cuadro de herramientas del Asignador en Visual Studio, no aparece ningún functoid en el cuadro de herramientas.  
  
 **Causa**  
  
 Es posible que se deba a un error en la instalación o desinstalación de los complementos y parches de Visual Studio.  
  
 **Resolución**  
  
 Para resolver este problema:  
  
1.  Cierre todas las instancias de ejecución de Visual Studio.  
  
2.  Iniciar **Visual Studio Command Prompt** como administrador.  
  
3.  En el símbolo del sistema, escriba el comando siguiente:  
  
    ```  
    devenv.exe /setup  
    ```