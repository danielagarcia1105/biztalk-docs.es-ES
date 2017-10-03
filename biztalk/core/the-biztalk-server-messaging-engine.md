---
title: "El motor de mensajería de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0c8d3e6-953d-4a04-adfc-b77ef7173464
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f8e0f4fa694699e2dfbc499b6f2fd3440656935
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-biztalk-server-messaging-engine"></a>Motor de mensajería de BizTalk Server
El motor de mensajería de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite a los usuarios crear procesos de negocio que abarquen varias aplicaciones al proporcionar dos elementos principales:  
  
-   Un modo de especificar e implementar la lógica que dirige el proceso empresarial.  
  
-   Un mecanismo para establecer comunicación entre las aplicaciones que utiliza el proceso empresarial.  
  
 La siguiente ilustración muestra los principales componentes del motor que afrontan estos dos problemas.  
  
 ![](../core/media/understandingbts-04-engine4.gif "UnderstandingBTS_04_Engine4")  
  
 Como se muestra en el diagrama, se recibe un mensaje a través de un **adaptador de recepción**. Los distintos adaptadores proporcionan diferentes mecanismos de comunicación, por lo que es posible que se pueda recibir un mensaje al tener acceso a un servicio Web, al leer un archivo o de otra manera. A continuación, se procesa el mensaje a través de un **canalización de recepción**. Esta canalización contiene distintos componentes que llevan a cabo funciones como, por ejemplo, convertir el mensaje de su formato original a un documento XML, validar la firma digital de un mensaje, etc. A continuación, se entrega el mensaje en una base de datos denominada el **MessageBox**, que se implementa mediante Microsoft SQL Server.  
  
 La lógica que dirige el proceso empresarial se implementa como uno o más **orquestaciones**, cada uno de los cuales consta de un código ejecutable. No obstante, estas orquestaciones no se crean mediante un código escrito en un lenguaje de programación como C#. En su lugar, un analista de negocios o, lo que es más probable, un programador, utiliza una herramienta apropiada para organizar gráficamente un grupo definido de formas con el fin de expresar condiciones, bucles y otros comportamientos. Orquestaciones pueden utilizar opcionalmente la **motor de reglas de negocios**, que proporciona una distinta y más sencilla forma de expresar conjuntos complejos de reglas en un proceso empresarial.  
  
 Cada orquestación crea **suscripciones** para indicar los tipos de mensajes que desea recibir. Cuando un mensaje apropiado llega al Cuadro de mensajes, dicho mensaje se entrega en la orquestación de destino, que llevará a cabo cualquier acción que necesite el proceso empresarial. El resultado de este procesamiento suele ser otro mensaje producido por la orquestación que se guarda en el Cuadro de mensajes. Este mensaje, a su vez, se procesa mediante un **canalización de envío**, que puede convertirlo del formato XML interno utilizado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el formato requerido por su destino, agregue una firma digital y mucho más. El mensaje se envía mediante un **del adaptador de envío**, que utiliza un mecanismo adecuado para comunicarse con la aplicación para la que se destina el mensaje.  
  
 Una completa **solución** basado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] motor puede contener distintas partes (a veces denominados artefactos): orquestaciones, canalizaciones, esquemas de mensaje y mucho más. Estas partes o artefactos pueden actuar como una sola unidad, que se conoce como un **aplicación de BizTalk**. Una aplicación de BizTalk incluye todas las piezas necesarias para integrar una solución en una sola unidad lógica. Esto la convierte en la abstracción fundamental para las acciones de administración e implementación.  
  
 Diferentes tipos de personas realizan distintas funciones con el motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. A **analista de negocios**, por ejemplo, podría definir las reglas y los comportamientos que componen un proceso empresarial. También determina el flujo del proceso empresarial, pues define la información que se envía a cada aplicación y cómo se asigna un documento empresarial a otro. Después de que el analista de negocios ha definido el proceso, un **developer** puede crear una aplicación de BizTalk que lo implementa. La implementación incluye tareas como la definición de esquemas XML para los documentos empresariales que se van a utilizar, la especificación de asignaciones detalladas entre ellos y la creación de las orquestaciones necesarias para implementar el proceso. Un **administrador** también desempeña un papel importante al configurar la comunicación entre las partes, implementar la aplicación de BizTalk de forma escalable y realizar otras tareas. Estos tres roles (analista de negocios, programador y administrador) son necesarios para la creación y el mantenimiento de soluciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Conectar sistemas](../core/connecting-systems.md)  
  
-   [Definir procesos empresariales](../core/defining-business-processes.md)  
  
-   [Administración y supervisión](../core/management-and-monitoring.md)  
  
-   [Enterprise Single Sign-On](../core/enterprise-single-sign-on-sso.md)  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de BizTalk Server](../core/biztalk-server-architecture.md)   
 [Arquitectura en tiempo de ejecución](../core/runtime-architecture.md)