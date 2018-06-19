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
ms.openlocfilehash: d1668c1f568a6cfb853957b3598b41f1cbdf6e33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225316"
---
# <a name="what-is-swiftnet"></a>¿Qué es SWIFTNet?
Como un solución estándar del sector para la industria financieros, de propósito general SWIFTNet proporciona una interfaz independiente de la aplicación, una sola ventana para todas las aplicaciones conectadas de todas las instituciones que participan en la Comunidad financiera global. El acceso real se controla por las decisiones de directiva de negocio de cada administrador de servicios, no por las limitaciones técnicas de la infraestructura.  
  
 SWIFTNet proporciona una base para garantizar que el negocio continuidad y recuperación ante desastres para la infraestructura de aplicaciones de misión crítica financieras que cruzan los límites institucionales. SWIFTNet está diseñado para cumplir los requisitos de la Comunidad institucional para la interoperabilidad de soluciones de software financiero una importancia decisiva.  
  
 Aplicaciones empresariales conectadas entre sí, SWIFTNet ofrece lo siguiente:  
  
-   Garantía de confiabilidad de la infraestructura  
  
-   Disponibilidad  
  
-   Control de acceso basado en roles y no basada en roles  
  
-   Autenticación corresponsal y mensaje  
  
-   Integridad del mensaje  
  
-   Confidencialidad  
  
-   Soporte sin rechazo  
  
-   Validación del mensaje  
  
-   Almacén y reenvío  

Usa SWIFTNet **SWIFTNet vínculo** (SNL) como la interfaz de programación de aplicaciones para los servicios de SWIFTNet y utiliza el **puerta de enlace de SWIFTAlliance** para la facilidad de uso y conectividad. Más información acerca de estos recursos en este tema.

## <a name="swiftnet-link-overview"></a>Información general sobre vínculos SWIFTNet

Aplicaciones de software empresarial utilizan la interfaz de programación de aplicaciones (API) de vínculo SWIFTNet (SNL) para acceder y usar los servicios de SWIFTNet. El SNL es la interfaz de red obligatorio para SWIFTNet. SWIFTNet requiere SNL para todas las interfaces externas. El SNL también incluye procesos en segundo plano que admiten la mensajería, seguridad y funciones de administración de servicio. El SNL se incorpora en SWIFTAlliance WebStation y SWIFTAlliance puerta de enlace (SAG).  
  
 SNL establece una relación de cliente/servidor de acoplamiento flexible entre los componentes de aplicación de negocios. En lugar de llamar directamente a métodos o funciones, la interacción está orientado a mensajes: los mensajes estructurados se pasan entre cliente y servidor. Una aplicación de negocio diseñada para servicios de SWIFTNet general consta de un conjunto de clientes y servidores. El mismo cliente o el mismo proceso del servidor se puede iniciar varias veces. Tenga en cuenta que no se puede predecir qué proceso se entregará la instancia de la misma aplicación una solicitud de mensaje entrante. Varios subprocesos dentro de un proceso de cliente pueden invocar la función de API de SwCall. Un proceso de servidor puede tener varios subprocesos también; Sin embargo, solo un subproceso puede invocar SwCallback. Procesos de cliente y el servidor no se puede combinar en el mismo proceso.  
  
 SNL proporciona un conjunto de características de nivel de transporte diseñado para entornos de alto rendimiento y alta disponibilidad. Entre estas características se incluyen:  
  
-   Equilibrio de carga  
  
-   Transparencia de ubicación y el enrutamiento, componentes de aplicación de la tecnología de transporte subyacente de blindaje  
  
-   Autenticación de nivel de transporte y confidencialidad, organizarse en SNL y proporciona de forma transparente a la aplicación  
  
-   Funciones de seguridad por qué empresa software de la aplicación puede establecer la seguridad de-to-end (aplicación de usuario para la aplicación de usuario), cuando sea necesario.  
  
 En términos de programación en el nivel de código fuente con C++ o Java, hay solo dos funciones: SwCall y SwCallback. SwCall se utiliza por las aplicaciones cliente para tener acceso a las aplicaciones de servidor a través de SWIFTNet. SwCallback se utiliza en aplicaciones de servidor para responder a los clientes a través de SWIFTNet.  
  
 Las funciones SwCall y SwCallback obtener acceso a la funcionalidad de SWIFTNet pasando los mensajes XML estructurados a y desde SWIFTNet. En tiempo de ejecución, SNL incluye dos bibliotecas de software, el código de los cuales se ejecuta en el mismo espacio de dirección como procesos de cliente o servidor de aplicaciones empresariales, y procesos independientes (demonios o servicios), que se ejecutan en sus propios espacios de direcciones. Las bibliotecas de software son accesibles a través de las API de SNL.  

## <a name="swiftalliance-gateway-overview"></a>Información general de la puerta de enlace de SWIFTAlliance
  
La puerta de enlace de SWIFTAlliance (SAG) es un producto de la interfaz para SWIFTNet. Incorpora también toda la funcionalidad del vínculo SWIFTNet. Además, proporciona varias características de uso y conectividad diferentes para los usuarios de SWIFTNet, proporcionar soluciones a una variedad de sistema problemas de integración.  
  
 El SAG admite varios modos diferentes de operación. Uno de ellos, el modo de vínculo SWIFTNet estricto, es especialmente relevante para los adaptadores FileAct e InterAct para SWIFT. En modo de vínculo de SWIFTNet strict, el SAG presenta una interfaz de mensajería que es funcionalmente equivalente a la interfaz de vínculo de SWIFTNet tal y como se describe a lo largo de estos temas.  
  
 El SAG actúa como un concentrador de mensaje. Recibe mensajes de varias otras aplicaciones y los pasa a través de SWIFTNet. Recibe estos mensajes a través de adaptadores de host, incluido un adaptador de host de WebSphere MQ, que permite a las aplicaciones de negocios con una variedad de distintos tipos de plataformas informáticas pasar los mensajes a través de SWIFTNet.  
 
 ## <a name="next-reading"></a>Lectura siguiente
 
 [¿Qué es el adaptador de FileAct?](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)  
 [¿Qué es el adaptador de interactuar?](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)  
 [BizTalk FileAct e interactuar Tutorial de adaptadores-to-End](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)
 
 ## <a name="see-also"></a>Vea también
 [Descripción de FileAct e interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)