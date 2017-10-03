---
title: Instalar el adaptador en BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1164468d-75a9-4116-87a6-6055948c198b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bc585e0574610a867d3f890ce456930bc936dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-adapter-into-biztalk-server"></a>Instalar el adaptador en BizTalk Server
Una vez escritas las entradas apropiadas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el Registro, es preciso agregar el adaptador a la base de datos de administración de BizTalk. Después de agregar el adaptador a esta base de datos, ya es un adaptador configurado de manera activa capaz de procesar mensajes cuando su configuración es correcta. Para instalar el adaptador en la base de datos se utiliza la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Después de instalar el adaptador en la base de datos, reinicie la instancia de host.  
  
> [!NOTE]
>  Para que esté visible y se pueda agregar en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un adaptador debe registrarse debidamente en el Registro HKLM e implementar las interfaces de adaptador necesarias.  
  
### <a name="to-install-the-static-sample-adapter"></a>Para instalar el adaptador estático de ejemplo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en el **grupo de BizTalk** nodo.  
  
3.  Expanda **configuración de plataforma** y seleccione **adaptadores**.  
  
4.  Haga clic en **adaptadores**, haga clic en **New**y, a continuación, haga clic en **adaptador**.  
  
5.  En el **propiedades del adaptador** diálogo cuadro, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |Nombre|Tipo de **estático**.|  
    |Adaptador|Seleccione **DotNetFile estático** en la lista desplegable.|  
    |Description|Tipo de **adaptador estático de ejemplo**.|  
  
6.  Haga clic en **Aceptar**.  
  
     El adaptador estático aparece en la lista de adaptadores, en la ventana derecha de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-stop-and-restart-the-host-instance"></a>Para detener y reiniciar la instancia de host  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en el **grupo de BizTalk** nodo.  
  
3.  Expanda **configuración de plataforma**, seleccione **Hosts**y, a continuación, seleccione **BizTalkServerApplication** en el panel de resultados.  
  
4.  Haga clic en la instancia de host (normalmente, el nombre del equipo) y, a continuación, haga clic en **detener**.  
  
     El estado de la instancia de host cambia a **detenido**.  
  
5.  En el panel de resultados, haga clic en la instancia de host y, a continuación, haga clic en **iniciar**.  
  
     El estado de la instancia de host cambia a **Inicio pendiente**. Debe hacer clic en **actualizar**, o haga clic en la instancia de host y, a continuación, haga clic en **actualizar**, para cambiar el estado a **ejecutando**.