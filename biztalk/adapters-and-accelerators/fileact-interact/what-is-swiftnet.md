---
title: ¿Qué es SWIFTNet? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b074385-352c-40f4-b73e-1891c627aa4e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02f09a1ccc9b67b084a6f683125bacaec5eae77c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989341"
---
# <a name="what-is-swiftnet"></a>¿Qué es SWIFTNet?
Como un solución estándar del sector para el sector financiero, de propósito general SWIFTNet proporciona una interfaz de ventana independiente de la aplicación, solo a todas las aplicaciones conectadas de todas las entidades que participan en la comunidad global financiera. Acceso real se controla por las decisiones de directiva de cada administrador de servicios de negocio, no por las limitaciones técnicas de la infraestructura.  
  
 SWIFTNet proporciona una base para asegurar el negocio continuidad y recuperación ante desastres para la infraestructura de aplicaciones financieras críticas que cruzan los límites institucionales. SWIFTNet está diseñado para satisfacer los requisitos de la Comunidad institucional para la interoperabilidad de soluciones de software financiero críticas.  
  
 Aplicaciones empresariales conectadas entre sí, SWIFTNet ofrece lo siguiente:  
  
-   Garantía de confiabilidad de la infraestructura  
  
-   Disponibilidad  
  
-   Control de acceso basado en roles y no basado en rol  
  
-   Autenticación de mensaje y corresponsal  
  
-   Integridad del mensaje  
  
-   Confidencialidad  
  
-   Soporte técnico sin repudio  
  
-   Validación de mensajes  
  
-   Store y reenvío  

Usa SWIFTNet **SWIFTNet vínculo** (SNL) como la interfaz de programación de aplicaciones a los servicios de SWIFTNet y usa el **SWIFTAlliance puerta de enlace** para la facilidad de uso y conectividad. Más información acerca de estos recursos en este tema.

## <a name="swiftnet-link-overview"></a>Información general sobre los vínculos de SWIFTNet

Aplicaciones de software empresarial usan la interfaz de programación de aplicaciones (API) del vínculo SWIFTNet (SNL) para obtener acceso y usar los servicios de SWIFTNet. El SNL es la interfaz de red obligatorio SWIFTNet. SWIFTNet requiere SNL para todas las interfaces externas. El SNL también incluye los procesos en segundo plano que admiten funciones de administración de servicios, seguridad y mensajería. El SNL se incorpora a SWIFTAlliance WebStation y puerta de enlace SWIFTAlliance (SAG).  
  
 SNL establece una relación de cliente/servidor de acoplamiento flexible entre los componentes de aplicación de negocios. En lugar de invocar directamente funciones o métodos, la interacción está orientado a mensajes: los mensajes estructurados se pasan entre cliente y servidor. Una aplicación de negocios diseñada para los servicios de SWIFTNet general consta de un conjunto de clientes y servidores. El mismo cliente o el mismo proceso de servidor se puede iniciar varias veces. Tenga en cuenta que no se puede predecir a qué proceso se entregará la instancia de la misma aplicación de una solicitud de mensaje entrante. Varios subprocesos dentro de un proceso de cliente pueden invocar la función API SwCall. Un proceso de servidor puede tener varios subprocesos Sin embargo, solo un subproceso puede invocar SwCallback. No se puede combinar los procesos de cliente y servidor en el mismo proceso.  
  
 SNL proporciona un conjunto de características de nivel de transporte diseñados para entornos de alto rendimiento y alta disponibilidad. Entre estas características se incluyen:  
  
- Equilibrio de carga  
  
- Transparencia de ubicación y el enrutamiento, componentes de la aplicación de la tecnología de transporte subyacente de blindaje  
  
- Autenticación de nivel de transporte y la confidencialidad, empaquetan dentro de SNL y proporciona de forma transparente a la aplicación  
  
- Las funciones de seguridad por qué business software de la aplicación puede establecer la seguridad de-to-end (aplicación de usuario para la aplicación de usuario), cuando sea necesario.  
  
  En términos de programación en el nivel de código de origen con C++ o Java, hay solo dos funciones: SwCall y SwCallback. SwCall se utiliza por las aplicaciones cliente para tener acceso a las aplicaciones de servidor a través de SWIFTNet. SwCallback se utiliza en aplicaciones de servidor para responder a los clientes a través de SWIFTNet.  
  
  Las funciones SwCall y SwCallback tener acceso a la funcionalidad de SWIFTNet al pasar los mensajes XML estructurados hacia y desde SWIFTNet. En tiempo de ejecución, SNL incluye las dos bibliotecas de software, el código que se ejecuta dentro del mismo espacio de direcciones como procesos de cliente o servidor de aplicaciones empresariales, y procesos independientes (demonios o servicios), que se ejecutan en sus propios espacios de direcciones. Las bibliotecas de software son accesibles a través de la API de SNL.  

## <a name="swiftalliance-gateway-overview"></a>Información general de la puerta de enlace SWIFTAlliance
  
La puerta de enlace SWIFTAlliance (SAG) es un producto de la interfaz de SWIFTNet. Incorpora toda la funcionalidad del vínculo SWIFTNet. Además, proporciona varias características de facilidad de uso y conectividad diferentes para los usuarios de SWIFTNet, soluciones de problemas de integración a una variedad de sistema.  
  
 El SAG admite varios modos diferentes de operación. Uno de ellos, el modo de vínculo de SWIFTNet estricto, es especialmente relevante para los adaptadores FileAct e InterAct para SWIFT. En modo de vínculo de SWIFTNet estricto, el SAG presenta una interfaz de mensajería que es funcionalmente equivalente a la interfaz de SWIFTNet vínculo como se describe en estos temas.  
  
 El SAG actúa como un concentrador de mensajes. Recibe mensajes de otras aplicaciones y los pasa a través de SWIFTNet. Recibe estos mensajes a través de adaptadores de host, incluido un adaptador de host WebSphere MQ, que permite a las aplicaciones de negocio que se ejecutan en una variedad de distintos tipos de plataformas informáticas pasar mensajes a través de SWIFTNet.  
 
 ## <a name="next-reading"></a>Lectura siguiente
 
 [¿Qué es el adaptador de FileAct?](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)  
 [¿Qué es el adaptador de InterAct?](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)  
 [Tutorial integral de los adaptadores de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)
 
 ## <a name="see-also"></a>Vea también
 [Descripción de la arquitectura de adaptador de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)