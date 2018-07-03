---
title: Identificar las posibles amenazas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd2feb0b6a09905efb7275b1cc6f0e6ef2b13d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972573"
---
# <a name="identifying-potential-threats"></a>Identificar las posibles amenazas
Puede utilizar el modelo STRIDE para identificar posibles amenazas para la implementación de BizTalk Server. STRIDE es un acrónimo derivado de las siguientes categorías: *S*identidad uplantación, *T*anipulación de datos, *R*epudio, *me* revelación de información *d.* enegación de servicio y elevación de privilegios. Esta sección contiene ejemplo de posibles amenazas para el entorno de BizTalk Server y mecanismos para mitigarlas.  
  
 **Suplantación de identidad**  
  
- Si se guardan las contraseñas en los archivos de enlace y éstos se guardan, los usuarios no autorizados podrían leerlas y usarlas para conectarse a los servidores de BizTalk y causar daños en éstos. Evite guardar las contraseñas en archivos de enlace y use listas de control de acceso discrecional (DACL) para restringir el acceso a archivos que puedan contener datos confidenciales.  
  
  **Manipulación de datos**  
  
- Los usuarios malintencionados pueden interceptar mensajes de los socios a BizTalk Server y modificar su contenido. Use firmas digitales para impedir que los usuarios malintencionados manipulen los mensajes mientras están en tránsito.  
  
  **Rechazo**  
  
- Es necesario realizar un seguimiento de los mensajes que envía y recibe BizTalk. Puede usar firmas digitales para probar que ha enviado, y que los socios le han enviado, mensajes.  
  
  **Divulgación de información**  
  
- Los usuarios malintencionados pueden leer la comunicación de texto sin cifrar entre BizTalk Server y Microsoft SQL Server™. Utilice la seguridad de Protocolo Internet (IPSec) o la Capa de sockets seguros (SSL) para garantizar la protección de las comunicaciones entre servidores. Puede usar servidores de seguridad para limitar el acceso a cada servidor. Puede usar el cifrado para garantizar la privacidad del mensaje mientras está en tránsito.  
  
- Puede que usuarios no autorizados obtengan acceso a información en recursos compartidos de red o directorios. Use listas seguras de control de acceso discrecional (DACL) para limitar el acceso a las cuentas que usan los recursos.  
  
- El administrador de Windows de un equipo que ejecuta una instancia de host de BizTalk podría llevar a cabo distintos niveles de ataques (por ejemplo, revelación de información o denegación del servicio). Sin embargo, en la mayoría de los casos, puede limitar estos ataques al host concreto cuyo equipo se ha visto comprometido por el atacante.  
  
  **Denegación de servicio**  
  
- Los usuarios malintencionados pueden enviar una gran cantidad de mensajes al servidor BizTalk Server para impedir que éste pueda recibir mensajes válidos. Para obtener más información acerca de las técnicas de mitigación esta amenaza, consulte [mitigación de ataques de denegación de servicio](../core/mitigating-denial-of-service-attacks.md).  
  
  **Elevación de privilegios**  
  
- Las amenazas de elevación de privilegios suelen producirse cuando se ejecuta en un entorno de confianza un código en el que no se confía o cuando un usuario malintencionado explota un error de software o de configuración. Debe asegurarse de que los ensamblados y los demás componentes que implementa en su entorno son de confianza. Para minimizar la posibilidad de un ataque de elevación de privilegios, utilice cuentas con permisos mínimos y que no se superpongan, y debería evitar el uso de cuentas administrativas para operaciones y servicios de tiempo de ejecución. También debe minimizar el número de componentes, aplicaciones y servicios que se ejecutan en el entorno.  
  
## <a name="see-also"></a>Vea también  
 [Denegación de servicio de mitigar los ataques](../core/mitigating-denial-of-service-attacks.md)   
 [Recomendaciones de seguridad para una implementación de BizTalk Server](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [Planear la seguridad](../core/planning-for-security.md)