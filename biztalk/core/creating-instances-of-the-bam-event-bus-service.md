---
title: Creación de instancias del servicio de Bus de sucesos SAE | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 454bdde7-45a6-41ab-9196-f662273f0f2b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afbe8f2e70baa3a963150991ced54a9d38adba88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238420"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a>Creación de instancias del servicio de Bus de eventos BAM
El servicio de bus de eventos BAM se ejecuta en un host de aplicación de BizTalk. Se puede utilizar el host predeterminado para alojar el servicio de bus de eventos BAM o, como alternativa, crear un nuevo host. Si un host aloja el servicio de bus de eventos BAM, todas las nuevas instancias de ese host que se creen   
  
 Para obtener información sobre el host predeterminado, consulte [Hosts](../core/hosts.md).  
  
 Para obtener información sobre la creación de hosts, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md).  
  
 Para obtener información sobre la creación de instancias de host, consulte [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md).  
  
 Para obtener información sobre cómo crear y configurar hosts e instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a>Para crear el host que alojará el servicio de bus de eventos BAM  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la ventana de consola de administración de BizTalk, expanda el **administración de BizTalk Server** nodo, expanda el **grupo de Biztalk** nodo y expanda el **configuración de plataforma** nodo , haga clic en el **Hosts** nodo, seleccione **New**y, a continuación, haga clic en **Host**.  
  
3.  En el **propiedades de Host** cuadro de diálogo, en la **nombre** cuadro, escriba un nombre descriptivo para el host.  
  
4.  En el **General** ficha, seleccione la **Permitir seguimiento de Host** casilla de verificación.  
  
     Aparece un nuevo nodo secundario en el **Hosts** nodo con el nombre del nuevo host.  
  
5.  En el **grupo de Windows** , escriba el nombre del grupo de Windows para asignar este host y, a continuación, haga clic en **Aceptar**.  
  
     Aparece un nuevo nodo secundario en el **Hosts** nodo con el nombre del nuevo host.  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a>Para crear una nueva instancia del host  
  
1.  Haga clic en el **instancia de Host** nodo, seleccione **New**y, a continuación, haga clic en **instancia de Host**.  
  
2.  Seleccione un servidor que ejecuta la instancia de host y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-add-hosting-tracking-to-the-host"></a>Para agregar el seguimiento de alojamiento al host  
  
1.  Haga clic en el host que desea volver a configurar y, a continuación, haga clic en **propiedades** .  
  
2.  En el **General** ficha, seleccione **Permitir seguimiento de Host**y, a continuación, haga clic en **Aceptar**.  
  
3.  Reinicie todas las instancias de ese host.  
  
### <a name="to-remove-hosting-tracking-from-the-host"></a>Para quitar el seguimiento de alojamiento del host  
  
1.  Haga clic en el host desde el que desea quitar el seguimiento de host y, a continuación, haga clic en **propiedades**.  
  
2.  Desactive el **Permitir seguimiento de Host** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
3.  Reinicie las instancias de ese host.  
  
## <a name="see-also"></a>Vea también  
 [Administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Actividad económica (BAM) de supervisión](../core/business-activity-monitoring-bam.md)