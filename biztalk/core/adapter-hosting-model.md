---
title: Adaptador de modelo para alojamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf9a8e6b-8c8d-47ec-b2a3-aed58206121d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645a1fcd41650c98c442549a898f7083be770842
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22225172"
---
# <a name="adapter-hosting-model"></a>Adaptador de modelo para alojamiento
En general, los adaptadores de BizTalk se hospedan en el servicio de BizTalk, Btsntsvc.exe. Esto significa que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administra la duración del adaptador. También hay situaciones, que se describen a continuación, en las que otros procesos administran el adaptador.  
  
## <a name="in-process-adapters"></a>Adaptadores de tipo En curso  
 Los adaptadores que se administran mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se denominan adaptadores en curso. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hace lo siguiente para estos adaptadores:  
  
-   Crear una instancia del adaptador al [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se inicia  
  
-   Transfiere el proxy de transporte del adaptador al adaptador durante la inicialización  
  
-   Atiende las solicitudes del adaptador  
  
-   Finaliza el adaptador apagado de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicio  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ofrece información de configuración de configuración y el punto de conexión de controlador para el adaptador en tiempo de ejecución. Se especifican otros aspectos de la configuración, tales como las ventanas de servicio que definen períodos de tiempo específicos durante los cuales el adaptador está habilitado para administrar solicitudes de forma activa.  
  
 El servicio BizTalk se puede apagar manualmente mediante la consola de administración [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o mediante el Administrador de control de servicios. Si la conectividad a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos se pierde automáticamente el servicio se recicla.  
  
 En el modelo de asignación de host típico, los adaptadores de recepción y los adaptadores envío están alojados en el mismo proceso que el servicio de BizTalk, junto con el motor de mensajería y el motor de orquestaciones. El modelo de asignación de host es lo suficientemente flexible como para permitir la separación de hosts de recepción y de envío, de orquestaciones y de cualquier combinación de ellos. En la siguiente ilustración, el host ejecuta los tres en el mismo proceso.  
  
 Durante el desarrollo de adaptadores conviene recordar que, gracias al modelo de asignación de host enriquecido, los adaptadores de envío y recepción tal vez nunca se configuren en el mismo host. Incluso pueden configurarse para que se ejecuten en equipos diferentes.  
  
 ![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")  
Modelo de asignación de host a adaptador de tipo En curso  
  
## <a name="isolated-adapters"></a>Adaptadores aislados  
 Hay escenarios en los que no es posible realizar la asignación de host de adaptadores de recepción en el servicio de BizTalk. Por ejemplo, en el modelo de proceso de Internet Information Services (IIS), IIS administra el período de vida de las aplicaciones ASP.NET y las extensiones ISAPI. El adaptador de SOAP de BizTalk, se debe ejecutar en el mismo espacio de proceso que IIS, lo que sea imposible que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para controlar la duración de las instancias del adaptador de SOAP.  
  
 Existe otro modelo de asignación de host para estos tipos de adaptadores y recibe el nombre de adaptadores de recepción aislados, o simplemente adaptadores aislados. No existe el concepto de adaptador de envío aislado.  
  
 Dado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se puede crear un adaptador aislado, el adaptador debe adquirir su propio proxy de transporte y registrarse con dicho proxy.  
  
 La ilustración siguiente muestra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] arquitectura de hospedaje. Por motivos de rendimiento, la arquitectura de host aislado intenta eliminar cualquier comunicación innecesaria entre procesos. Dado que el adaptador aislado y la pila del motor de mensajería de BizTalk están en el mismo proceso, no existe comunicación entre procesos cuando el adaptador llama al motor de mensajería. En este escenario, la única comunicación existente entre procesos es la que se produce entre el motor de mensajería y la base de datos, la cual es inevitable.  
  
 ![](../core/media/isolatedadapters.gif "IsolatedAdapters")  
Modelo de asignación de host a adaptador aislado  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el marco de trabajo de adaptadores?](../core/what-is-the-adapter-framework.md)