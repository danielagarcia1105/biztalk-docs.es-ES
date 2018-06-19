---
title: 'Paso 1: Crear un Namespace de Bus de servicio | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d7630316f72fd63bac5ce7127b5451683e2f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276764"
---
# <a name="step-1-create-a-service-bus-namespace"></a>Paso 1: Crear un Namespace de Bus de servicio
En este paso, creará un [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)] espacio de nombres. Usará este espacio de nombres para hospedar un extremo de retransmisión para la recepción de notificaciones de oportunidades de Salesforce. Más adelante en el proceso de creación de esta solución, usará este extremo de retransmisión para recibir el mensaje de notificación en un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a>Para crear un espacio de nombres de [!INCLUDE[sb](../includes/sb-md.md)]  
  
1.  Inicie sesión en [http://manage.windowsazure.com](http://manage.windowsazure.com) con su cuenta de Microsoft.  
  
2.  En la parte inferior de la página, haga clic en **New**, **servicios de aplicaciones**, **Service Bus Relay**y, a continuación, **creación rápida**.  
  
3.  Escriba el espacio de nombres como `BtsSalesforce` y seleccione la región más cercana a su ubicación geográfica actual. Haga clic en **crear una retransmisión**.  
  
    > [!CAUTION]
    >  Este espacio de nombres debe ser único global. Por tanto, debe usar un espacio de nombres que no se mencione en este tutorial.  
  
    > [!NOTE]
    >  Tenga en cuenta que la retransmisión no se crea como parte de la operación, solo el espacio de nombres. El extremo de retransmisión se crea más adelante en este tutorial, cuando se configura una ubicación de recepción para el **SB-Messaging** adaptador.  
  
4.  Después de crea el espacio de nombres, el estado se establece en **Active**. Una vez que el estado está activo, puede seleccionar el espacio de nombres y haga clic en **clave de acceso** en la parte inferior de la página para obtener detalles sobre cómo conectarse a la **BtsSalesforce** espacio de nombres, incluidos los valores de **Usuario predeterminado** y **clave predeterminada**. Necesitará estos detalles más adelante en el tutorial.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: 6: Integración de BizTalk Server 2013 con Salesforce](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)