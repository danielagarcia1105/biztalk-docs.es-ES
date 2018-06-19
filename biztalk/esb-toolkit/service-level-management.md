---
title: Administración del nivel de servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add50343-5470-4db3-a029-c827523e2f2c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b7ba1672660af2a68a5d193729a0a9009173d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294732"
---
# <a name="service-level-management"></a>Administración del nivel de servicio
El Administrador de nivel de servicio de SMS de AmberPoint proporciona visibilidad a específicos de problemas de rendimiento y disponibilidad en sistemas basados en SOA de nivel de empresa. Instrumenta y realiza un seguimiento de las métricas para cada Microsoft BizTalk Server ubicación de recepción y el puerto de envío. Esto proporciona la indicación de estado en tiempo real, además de caracterización de rendimiento en curso de estos componentes. La figura 1 muestra la visualización de las métricas asociadas a una ubicación de recepción.  
  
 ![Ubicación de recepción AmberPoint](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9-AmberPointReceiveLocation")  
  
 **Figura 1**  
  
 **Las métricas asociadas a una ubicación de recepción**  
  
 Análisis en tiempo de ejecución AmberPoint permiten a los usuarios establecer umbrales y enviar alertas cuando un sistema supera un umbral de un evento crítico, incluidos los eventos de advertencias de conformidad, eventos de infracciones de cumplimiento de normas y un retorno posterior al cumplimiento de normas. La figura 2 muestra la pantalla donde los usuarios configurar acuerdos de nivel de servicio y ver las alertas generadas para este contrato de nivel de servicio.  
  
 ![SLA AmberPoint](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")  
  
 **Figura 2**  
  
 **Las pantallas para configurar un contrato de nivel de servicio y ver las alertas**  
  
 Puede establecer objetivos de rendimiento dentro del Administrador de nivel de servicio. A continuación, el software realiza un seguimiento de los mensajes individuales, mensajes de un usuario específico o mensajes de grupos de usuarios para medir el rendimiento en estos destinos.  
  
 También puede configurar directivas de registro que indique a AmberPoint SMS dinámicamente recopilar e inspeccionar el contexto del mensaje y los datos que pasan a través de BizTalk Server, como se muestra en la figura 3. A continuación, puede utilizar estos registros para solucionar el problema "sobre la marcha", para el análisis técnico de problemas y para archivar para cumplir con las normas específicas de la industria.  
  
 ![Mensajes de servicio de BizTalk](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9-BizTalkServiceMessages")  
  
 **Figura 3**  
  
 **El archivo de registro de mensajes del servicio de BizTalk Server**