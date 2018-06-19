---
title: Problemas conocidos con el adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe3093416a10b6b66867dcb2e3629de8f25e5aca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262204"
---
# <a name="known-issues-with-the-mqseries-adapter"></a>Problemas conocidos del adaptador de MQSeries
Esta sección contiene información que puede servir de ayuda para evitar errores.  
  
## <a name="know-issues"></a>Problemas conocidos  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a>Los errores de acceso denegado se producen al intentar enviar o recibir mensajes  
  
##### <a name="problem"></a>Problema  
 Cuando se utiliza el adaptador de MQSeries para mandar mensajes a o recibir mensajes de un servidor MQSeries, los errores similares al siguiente se registran en el registro de la aplicación del Visor de eventos:  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  En este mensaje de error, *servername* es el nombre del servidor y *queuename* es el nombre de la cola.  
  
 Asimismo, al intentar crear la ubicación de recepción o el puerto de envío que está configurado para utilizar el adaptador de BizTalk para MQSeries, puede que visualice el siguiente mensaje de advertencia en el Visor de eventos:  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a>Causa  
 Este problema se puede producir cuando se cumplen una o más de las condiciones siguientes:  
  
-   La cuenta de host para el adaptador de MQSeries no tiene los permisos requeridos para la aplicación MQSAgent COM+ en el servidor de MQSeries.  
  
-   En un servidor basado en [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], la cuenta de host para el adaptador de MQSeries no es un miembro del grupo Usuarios de COM distribuido en el servidor de MQSeries.  
  
##### <a name="resolution"></a>Solución  
 Para solucionar este problema, utilice los métodos siguientes. Si un método no soluciona este problema, pruebe con el método siguiente.  
  
 **Método 1: Habilitar el acceso de red COM + en Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-equipo basado en**  
  
 Habilite el acceso de red COM + en Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-equipo basado en siguiendo los pasos documentados en [cómo habilitar el acceso de red COM + en Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=67076).  
  
 **Método 2: Configurar MSDTC**  
  
 Siga los pasos de la **establecer las opciones de configuración de seguridad de MSDTC en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]**  sección de [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md) para configurar MSDTC.  
  
 **Método 3: Compruebe que la cuenta del host se agrega a la función en la aplicación MQSAgent COM +**  
  
 Compruebe que la cuenta de host para el adaptador de MQSeries se ha agregado a la función que se creó en la aplicación MQSAgent COM+ del servidor MQSeries. Esto lo puede comprobar en la interfaz de administración Servicios de componente.  
  
 **Método 4: Comprobar que la cuenta de host para el adaptador de MQSeries es miembro del grupo de usuarios de COM distribuido**  
  
 En un servidor basado en Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], examine los miembros del grupo de la cuenta de host para el adaptador de MQSeries. Asegúrese de que la cuenta es miembro de la **usuarios COM distribuidos** grupo en el servidor de MQSeries donde está instalada la aplicación MQSAgent COM +.  
  
 Para obtener más información acerca de las mejoras de seguridad DCOM en Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], consulte [mejoras de seguridad DCOM](http://go.microsoft.com/fwlink/?LinkId=67077).  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador de MQSeries](../core/troubleshooting-the-mqseries-adapter.md)