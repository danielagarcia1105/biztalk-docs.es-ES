---
title: "Importar el módulo de administración de supervisión de BizTalk Server 2013 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bee2bfe9-4eb0-46d4-8eee-75182202080c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6dff55cce17d9b9159a8eca754f91373621929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a>Importar el módulo de administración de supervisión de BizTalk Server 2013
Para obtener instrucciones sobre cómo importar un módulo de administración, vea cómo importar un módulo de administración en [Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=142351) (http://go.microsoft.com/fwlink/?LinkId=142351). Después de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se importa el módulo de administración, siga estos procedimientos para finalizar la configuración inicial:  
  
### <a name="to-configure-the-management-pack"></a>Para configurar el módulo de administración  
  
1.  Crear un nuevo módulo de administración en el que almacenar invalidaciones y otras personalizaciones.  
  
2.  Para habilitar a la configuración de Proxy del agente, siga estos pasos:  
  
    1.  Abra la consola del operador y, a continuación, haga clic en el botón administración.  
  
    2.  En el panel Administrador, haga clic en **administrado con agente**.  
  
    3.  Haga doble clic en un agente en la lista.  
  
    4.  En la ficha seguridad, seleccione **permitir que este agente actúe como proxy y detectar objetos administrados en otros equipos**.  
  
    5.  Repita los pasos 3 y 4 para cada agente que está instalado en un servidor BizTalk Server.