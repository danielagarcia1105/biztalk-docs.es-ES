---
title: Arquitectura del marco de trabajo de reglas de negocios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, caching
- Business Rules Framework, Rule Engine Update service
- rule store [Business Rules Framework]
- Policy class [Business Rules Engine]
- Business Rules Framework, architecture
- Business Rules Framework, RuleEngine class
- Business Rules Framework, Policy class
- Business Rules Framework, authoring tools
- RuleEngine class [Business Rules Engine]
- caching, Business Rules Framework
- Business Rules Framework, fact retrievers
- architecture, Business Rules Framework
- Business Rules Framework, rule store
ms.assetid: f5570cca-7664-4180-af9c-64ef90a0022b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55c624f8eaac517d11774ec2c542bf4ddbe0351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971845"
---
# <a name="business-rules-framework-architecture"></a>Arquitectura del marco de trabajo de reglas de negocios
En la siguiente ilustración se muestra la arquitectura de componentes del marco de trabajo de reglas de negocios.  
  
 ![Arquitectura de componentes de marco de reglas de negocio](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")  
Arquitectura del marco de trabajo de reglas de negocios de Microsoft  
  
 En los párrafos siguientes se describen algunos de los componentes del marco de trabajo.  
  
## <a name="policy-class"></a>Clase Directiva  
 Un **directiva** objeto es una instancia única de una directiva empresarial y proporciona la interfaz que usa las aplicaciones basadas en reglas. Proporciona una abstracción que libera de preocupaciones al programador de aplicaciones respecto a la ubicación del almacén de reglas, pues extrae los conjuntos de reglas del almacén de reglas, crea instancias a partir de instancias del motor de reglas subyacentes y garantiza que los hechos a largo plazo se imponen en el motor. En muchos escenarios, una aplicación basada en reglas utiliza instancias simultáneas de la **directiva** objeto. Estas instancias simultáneas pueden representar la misma directiva, distintas versiones de la misma directiva o versiones diferentes de directivas dispares.  
  
## <a name="ruleengine-class"></a>Clase RuleEngine  
 El **RuleEngine** objeto actúa como el motor de ejecución para las directivas empresariales. Usa tres componentes complementarios (traductor, motor de inferencia e interceptor de seguimiento) para la implementación. Un **RuleEngine** objeto toma un **RuleSet** objeto que representa una directiva empresarial como entrada y usa el traductor, motor de inferencia y el interceptor de seguimiento configurado para el conjunto de reglas para implementar la establece la directiva empresarial definida por la regla.  
  
## <a name="fact-retriever"></a>Almacenes de datos  
 Un administrador de almacenes de datos es un componente complementario opcional y definido por el usuario que se encarga de recopilar hechos a largo plazo para utilizarlos en directivas empresariales. Para obtener más información, consulte [cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md).  
  
 Antes de la ejecución, un **directiva** instancia de objeto proporciona su **RuleEngine** memoria de trabajo de la instancia para el Administrador de almacenes, dándole la oportunidad de actualizar el conjunto de hechos en el motor de reglas. Para obtener más información, consulte [frente a hechos a corto plazo. Hechos a largo plazo](../core/short-term-facts-vs-long-term-facts.md).  
  
## <a name="rule-engine-update-service"></a>Servicio de actualización de motor de reglas  
 El Servicio de actualización de motor de reglas proporciona actualizaciones dinámicas de directivas empresariales en un entorno distribuido. Una aplicación de servicio de Microsoft Windows NT de inicio automático se encarga de realizar suscripciones a los eventos de implementación y de anulación de implementación que se producen tras el cambio de directivas empresariales.  
  
 En un escenario empresarial común, las directivas empresariales se implementan tras actualizarse, probarse y realizarse versiones de ellas. La implementación consiste en agregar la directiva actualizada a un almacén de reglas seguro y persistente. Además, en ciertos casos se ejecuta una lógica en el almacén para publicar la información acerca de la directiva actualizada en todas las entidades implicadas (tenga en cuenta que es la información de la directiva lo que se publica, y no la directiva en sí).  
  
 El Servicio de actualización de motor de reglas, que se ejecuta en un servidor que aloja aplicaciones basadas en reglas, recibe la notificación de actualización de directivas y almacena la información en caché para usos posteriores. El empleo de un modelo de publicación y suscripción (pub/sub) en las actualizaciones de directivas le permite cambiar directivas empresariales casi en tiempo real sin que se produzcan interrupciones ni tiempos de inactividad en el servicio.  
  
## <a name="policyvocabulary-authoring-tools"></a>Herramientas de creación de directivas y vocabularios  
 El Compositor de reglas de negocio en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona directivas y vocabularios funciones a los usuarios finales y a los desarrolladores de creación.  
  
## <a name="rule-store"></a>Almacén de reglas  
 Un *almacén de reglas* es un repositorio de vocabularios y directivas empresariales. El repositorio puede ser un archivo simple o una base de datos confiable, persistente, escalable y segura como, por ejemplo, Microsoft SQL Server. (SQL Server se utiliza en el marco de trabajo como el almacén de reglas predeterminado).  
  
## <a name="caching"></a>Almacenamiento en memoria caché  
 El marco de motor de reglas de negocios proporciona un mecanismo de almacenamiento en caché para **RuleEngine** instancias. Cada **RuleEngine** instancia contiene una representación en memoria de una versión de directiva específica.  
  
 Los pasos siguientes describen el proceso cuando un nuevo **directiva** se crea una instancia de instancia (ya sea con una llamada a la API o la ejecución de la **reglas de llamada** forma):  
  
1. El **directiva** objeto solicitudes un **RuleEngine** instancia desde la caché del motor de reglas.  
  
2. Si un **RuleEngine** instancia por la versión de directiva que exista en la memoria caché, el **RuleEngine** instancia se devuelve a la **directiva** objeto. Si un **RuleEngine** instancia no está disponible, la memoria caché crea una nueva instancia. Cuando un **RuleEngine** se crea una instancia de instancia, lo hace, a su vez, cree una nueva instancia de almacenes de datos de hechos, si hay uno configurado para la versión de directiva.  
  
   Cuando el **Execute** se llama al método en el **directiva** de objeto, se producen los pasos siguientes:  
  
3. El objeto de directiva llama a la **UpdateFacts**método en la instancia de almacenes de datos de hecho, si existe un administrador de almacenes. Implementación de almacenes del método puede imponer hechos a largo plazo en la memoria de trabajo de la **RuleEngine**.  
  
4. El **directiva** objeto impone los hechos a corto plazo incluidos en el **matriz** que se pasó el **Execute** llamar.  
  
5. El **directiva** de objeto llama **Execute** en el **RuleEngine**.  
  
6. El **RuleEngine** completa la ejecución y devuelve el control a la **directiva**objeto.  
  
7. El**directiva**objeto retira los hechos a corto plazo la **RuleEngine**. Los hechos a largo plazo impuestos por el administrador de almacenes de datos permanecerán en la memoria de trabajo del motor de reglas.  
  
   Después de la **Dispose** se llama al método en el **directiva** objeto, el **RuleEngine** se libera la instancia a la caché del motor de reglas.  
  
   La memoria caché del motor de reglas dispondrá de varias instancias del motor de reglas para una versión de directiva determinada si la carga lo requiere, y cada instancia del motor de reglas contará con su propia instancia del administrador de almacenes de datos.  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas de negocio](../core/business-rules-engine.md)