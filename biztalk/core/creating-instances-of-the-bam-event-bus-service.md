---
title: Creación de instancias de servicio de Bus de eventos BAM | Microsoft Docs
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
ms.openlocfilehash: daf847afc8f5c1d284a8266d70006a0f43508ed9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984005"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a>Creación de instancias de servicio de Bus de eventos BAM
El servicio de bus de eventos BAM se ejecuta en un host de aplicación de BizTalk. Se puede utilizar el host predeterminado para alojar el servicio de bus de eventos BAM o, como alternativa, crear un nuevo host. Si un host aloja el servicio de bus de eventos BAM, todas las nuevas instancias de ese host que se creen   
  
 Para obtener información sobre el host predeterminado, consulte [Hosts](../core/hosts.md).  
  
 Para obtener información sobre la creación de hosts, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md).  
  
 Para obtener información sobre la creación de instancias de host, consulte [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md).  
  
 Para obtener información sobre la creación y configuración de hosts e instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a>Para crear el host que alojará el servicio de bus de eventos BAM  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En la ventana de consola de administración de BizTalk, expanda el **administración de BizTalk Server** nodo, expanda el **grupo de Biztalk** nodo y expanda el **configuración de plataforma** nodo , haga clic en el **Hosts** nodo, seleccione **New**y, a continuación, haga clic en **Host**.  
  
3. En el **propiedades de Host** cuadro de diálogo el **nombre** cuadro, escriba un nombre descriptivo para el host.  
  
4. En el **General** ficha, seleccione el **Permitir seguimiento de Host** casilla de verificación.  
  
    Aparece un nuevo nodo secundario bajo el **Hosts** nodo con el nombre del nuevo host.  
  
5. En el **grupo Windows** , escriba el nombre del grupo de Windows para asignar el host y, a continuación, haga clic en **Aceptar**.  
  
    Aparece un nuevo nodo secundario bajo el **Hosts** nodo con el nombre del nuevo host.  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a>Para crear una nueva instancia del host  
  
1.  Haga clic en el **instancia de Host** nodo, seleccione **New**y, a continuación, haga clic en **instancia de Host**.  
  
2.  Seleccione un servidor que ejecute la instancia de host y, a continuación, haga clic en **Aceptar**.  
  
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
 [Supervisión de la actividad económica (BAM)](../core/business-activity-monitoring-bam.md)