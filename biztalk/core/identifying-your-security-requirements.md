---
title: Identificar los requisitos de seguridad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, configuring
- planning, security
- security, planning
ms.assetid: 5a12c959-59b5-4d44-b2f4-e1ed7053ffd5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea9b21cfdfe722d80779dcf9098355b9a5ae3727
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257636"
---
# <a name="identifying-your-security-requirements"></a>Identificar los requisitos de seguridad
Las respuestas a las preguntas siguientes le ayudarán a planear la mejor forma de implementar BizTalk Server en su entorno.  
  
|Pregunta|Recomendación|  
|--------------|--------------------|  
|¿Cómo debe implementarse BizTalk Server en un entorno seguro?|La respuesta a esta pregunta depende de las necesidades específicas de los entornos, de los activos de la compañía, de lo vulnerables de éstos sean a posibles amenazas y de cómo desee protegerlos. Es importante realizar un análisis de modelo de amenazas para determinar los principales activos que desea proteger.<br /><br /> [Arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md) proporciona recomendaciones para proteger su entorno de BizTalk Server. Una vez realizado el modelo de amenazas, use la información de esta sección para diseñar su propia implementación segura de BizTalk Server.|  
|¿Piensa usar Supervisión de la actividad económica (BAM)?|Para usar los servicios BAS, es preciso que los usuarios empresariales de la red corporativa obtengan acceso a los recursos de BizTalk Server. Si usa esta función, deberá tener en cuenta algunas recomendaciones de seguridad adicionales a la hora de diseñar la implementación de BizTalk Server. Para obtener más información, consulte [arquitectura de distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md).|  
|¿Cuál es la mejor manera de proteger las funciones de BizTalk Server que planea utilizar?|Para obtener recomendaciones generales sobre cómo proteger un entorno de BizTalk Server, vea [recomendaciones de seguridad para una implementación de BizTalk Server](../core/security-recommendations-for-a-biztalk-server-deployment.md).<br /><br /> Para obtener recomendaciones sobre cómo proteger las diferentes características de BizTalk Server, vea el tema sobre seguridad correspondiente a cada característica.|  
|¿Cuáles son las posibles amenazas a las que se expone el entorno de BizTalk?|Para obtener más información, consulte [identificar posibles amenazas](../core/identifying-potential-threats.md).|  
|¿Cuáles son las posibles amenazas para la implementación de BizTalk Server y cómo se pueden mitigar?|Para identificar las posibles amenazas a las que se expone el entorno y cómo mitigarlas, deber realizar un análisis de modelo de amenazas. Para obtener más información acerca del modelado de amenazas, consulte el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/?LinkId=25224](http://go.microsoft.com/fwlink/?LinkId=25224).|  
|¿Cómo puede proteger su entorno de ataques de denegación del servicio?|Los ataques de denegación de servicio son los más difíciles de mitigar. Aunque el entorno no se puede proteger completamente contra estos ataques, puede realizar algunas acciones para mitigar su impacto. Para obtener más información, consulte [mitigación de ataques de denegación de servicio](../core/mitigating-denial-of-service-attacks.md).|  
|¿Qué puertos deben abrirse en los servidores de seguridad para los servicios de BizTalk?|Para obtener más información, consulte [los puertos necesarios para que BizTalk Server](../core/required-ports-for-biztalk-server.md).|  
|¿Qué cuentas debe utilizar en una implementación distribuida de BizTalk Server?|Aunque las cuentas concretas que se usen en el entorno dependen de los servicios que se utilicen, se recomienda emplear grupos y cuentas diferentes para los distintos servicios. Para obtener más información, consulte [cuentas de Windows para una implementación segura distribuida BizTalk Server](../core/windows-accounts-for-a-secure-distributed-biztalk-server-deployment.md).|  
  
## <a name="see-also"></a>Vea también  
 [Planear la seguridad](../core/planning-for-security.md)   
 [Recomendaciones de seguridad para una implementación de BizTalk Server](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [Identificar las posibles amenazas](../core/identifying-potential-threats.md)   
 [Denegación de servicio de mitigar los ataques](../core/mitigating-denial-of-service-attacks.md)