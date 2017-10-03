---
title: "Cómo configurar el seguimiento de una canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [pipelines], tracking warning
- tracking, pipelines
- tracking, warnings
- configuring, pipelines
- pipelines, tracking
- managing [pipelines], configuring
- tracking, configuring
- pipelines, configuring
- configuring [HAT tracking], pipelines
- HAT, pipelines
- managing [pipelines], tracking
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e933e9b50c99e11013ceaedf65c4f253ad1620c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-pipeline"></a>Cómo configurar el seguimiento de una canalización
En este tema se explica cómo utilizar la consola de administración de BizTalk Server para configurar el seguimiento de una canalización. Puede que desee configurar el seguimiento con fines de solución de problemas y auditoría. Puede ver propiedades de mensajes, eventos de puerto y eventos de mensajes. También puede realizar un seguimiento de eventos de mensaje y eventos de puerto para mensajes.  
  
 Puede configurar el seguimiento de una de las canalizaciones predeterminadas incluidas en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], o bien de una canalización personalizada que se haya implementado en una aplicación de BizTalk. Los parámetros de seguimiento que haya definido se aplicarán a todas las instancias de la canalización.  
  
> [!IMPORTANT]
>  Aunque se puede configurar el seguimiento de una canalización, esto generará una gran cantidad de datos, pues los datos se recopilan globalmente para todos los puertos que utilizan la canalización. Se recomienda en su lugar que configurar el seguimiento de su envío y puertos de recepción, como se describe en [cómo configurar seguimiento para un puerto de envío](../core/how-to-configure-tracking-for-a-send-port.md) y [cómo configurar seguimiento para un puerto de recepción](../core/how-to-configure-tracking-for-a-receive-port.md).  
  
 Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-tracking-for-a-pipeline"></a>Para configurar el seguimiento de una canalización  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server** y expanda el grupo de BizTalk que contenga la canalización cuyo seguimiento desea configurar.  
  
3.  Realice una de las siguientes operaciones:  
  
    -   Para configurar el seguimiento para una de manera predeterminada las canalizaciones de BizTalk, expanda \<todos los artefactos >.  
  
    -   Para configurar el seguimiento para una canalización personalizada que se ha implementado en una aplicación de BizTalk, expanda la aplicación que contiene la canalización.  
  
4.  Haga clic en el **canalizaciones** carpeta, haga clic en la canalización y, a continuación, haga clic en **seguimiento**.  
  
    > [!NOTE]
    >  Para configurar el seguimiento de varias canalizaciones a la vez, mantenga presionada la tecla MAYÚS, haga clic en cada canalizaciones que desea configurar, haga clic en una de las canalizaciones y, a continuación, haga clic en **seguimiento**.  
  
5.  Configurar opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Puerto eventos de inicio y finalización**|Realizar un seguimiento sólo cuando se inicia y finaliza una instancia (casilla activada). Los detalles incluyen el nombre de elemento, el ensamblado y otros metadatos.|  
    |**Mensaje de enviar y recibir eventos**|Active esta casilla de verificación para realizar un seguimiento de los eventos de envío y recepción de mensajes. Esta casilla de verificación está disponible solo si **eventos de inicio y fin de puerto** está seleccionada.|  
    |**Mensajes antes del procesamiento de canalización**|Guardar y realizar un seguimiento de los cuerpos de mensaje recibidos por la canalización, que contendrán metadatos tales como URL o propiedades promovidas (casilla activada). Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje sin procesar que envía el componente de transporte a la canalización. En función de la aplicación, el mensaje podría estar cifrado, firmado o codificado. Al utilizar una asignación de BizTalk, si se trata de una canalización de recepción, el seguimiento se efectúa después de que se procese la asignación de entrada.<br /><br /> Esta casilla de verificación está disponible solo si **envío de mensajes y recibir eventos** está seleccionada.|  
    |**Mensajes después del procesamiento de canalización**|Guardar y realizar un seguimiento de los cuerpos de mensaje enviados por la canalización, que contendrán metadatos tales como URL o propiedades promovidas (casilla activada). Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje procesado que se va a enviar a la base de datos de cuadro de mensajes, que puede ser XML, según la aplicación que utilice. Al utilizar una asignación de BizTalk, si se trata de una canalización de envío, el seguimiento se efectúa antes de que se procese la asignación de salida.<br /><br /> Esta casilla de verificación está disponible solo si **envío de mensajes y recibir eventos** está seleccionada.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar canalizaciones](../core/managing-pipelines.md)