---
title: 'Tutorial 1: Integración de aplicaciones empresariales | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial
- getting started tutorials, integrating enterprise applications
- enterprise application integration tutorial, about the tutorial
ms.assetid: aca5fc97-0fd6-4964-9cf1-482aa4f444b8
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6ddbd6c2a3e25619c684036eee3fb0fa46a18f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287516"
---
# <a name="tutorial-1-enterprise-application-integration"></a>Tutorial 1: Enterprise Application Integration
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un entorno de desarrollo y en tiempo de ejecución para la integración de aplicaciones y la administración de procesos empresariales (BPM). En este tutorial se presenta un ejercicio completo sobre la configuración e implementación de una solución de integración de aplicaciones de negocio (EAI) con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##  <a name="BKMK_Tut1_scenario"></a>Escenario empresarial  
 Contoso es una tienda en línea que vende hardware y software informáticos.  La empresa ha adquirido recientemente un sistema de planeamiento de recursos empresariales (ERP) con el fin de administrar sus recursos.  En este tutorial, desarrollará una solución de Enterprise Application Integration (EAI) mediante BizTalk Server para integrar un sistema de almacén existente con el sistema ERP y automatizar el proceso de solicitudes de almacén.  
  
 Esta solución de integración presenta varios retos:  
  
-   **Transporte de mensajes**.  El sistema de almacén y el sistema ERP pueden residir en dos plataformas diferentes y usar diferentes protocolos de transporte para enviar y recibir mensajes. Esta solución debe poder recibir los mensajes mediante los protocolos que admite el sistema de envío y reenviar los mensajes mediante los protocolos que admite el sistema de recepción.  BizTalk Server utiliza *adaptadores* para transportar mensajes.  La instalación de BizTalk Server y el paquete de adaptadores de BizTalk incluyen varios adaptadores nativos.  Para adaptadores adicionales, puede adquirirlos a proveedores o bien desarrollar adaptadores propios mediante los marcos de trabajo de adaptadores que proporciona BizTalk Server. Para obtener más información acerca de los adaptadores, vea [http://go.microsoft.com/fwlink/?LinkId=191131](http://go.microsoft.com/fwlink/?LinkId=191131).  
  
-   **Conversión de mensajes**. Existen varios tipos de mensajes, tal como eXtended Markup Language (XML), Electronic Data Interchange (EDI), archivos delimitados, etc. BizTalk Server se centra en XML. En la mayoría de los casos, puede convertir los mensajes entrantes en XML primero.  Este proceso se denomina *análisis*.  En el lado saliente, puede convertir mensajes de XML a otros tipos.  Este proceso se denomina *serialización*.  
  
-   **Administración de procesos empresariales**. La mayoría de los escenarios de EAI hace más que limitarse a reenviar mensajes de un sistema a otro.  Normalmente implican más sistemas y flujos de trabajo complejos.  En este escenario, el almacén envía un mensaje que solicita la reposición del inventario. La solución recibe el mensaje y posteriormente comprueba el total general de la solicitud.  Si el total general supera una determinada cantidad, la solución rechaza automáticamente la solicitud y envía un mensaje de rechazo; en caso contrario, la solución reenvía la solicitud al sistema ERP.  
  
     En el diagrama siguiente se muestra el proceso empresarial:  
  
     ![Flujo de mensajes del tutorial 1](../core/media/tut1-msg-flow.gif "tut1_msg_flow")  
  
 En este tutorial, las herramientas de desarrollo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usan para diseñar e implementar el proceso empresarial.  
  
## <a name="preparation"></a>Preparación  
 Debe recopilar cierta información básica antes de crear una solución de integración de BizTalk Server:  
  
-   ¿Cuántas aplicaciones o sistemas debe integrar la solución de BizTalk Server?  En este escenario, hay dos sistemas: el sistema ERP y el sistema de almacén.  
  
-   ¿Qué protocolos de transporte admite cada una de las aplicaciones?  Para simplificar la solución, supondremos que ambas aplicaciones usan archivos.  El sistema de almacén envía la solicitud como archivo en una carpeta de archivos. La solución de BizTalk Server recoge el archivo de la carpeta, lo procesa y suelta la solicitud en otra carpeta que supervisa el sistema ERP.  
  
-   ¿Qué tipos de mensaje usan las aplicaciones?  Para simplificar la solución, supondremos que ambas aplicaciones usan el tipo XML. Los esquemas y documentos BizTalk que definen la estructura de los datos de XML en los mensajes de BizTalk y su finalidad es crear plantillas para procesar y validar mensajes XML. BizTalk Server incluye un Editor de BizTalk para crear esquemas de BizTalk.  
  
-   ¿Qué es el proceso empresarial?  El proceso se ha explicado previamente en este título.  
  
## <a name="biztalk-server-architecture"></a>Arquitectura de BizTalk Server  
 Resulta útil comprender cómo BizTalk Server ejecuta la solución.  En la siguiente ilustración se muestra el flujo de datos por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 ![Flujo de datos de escenario de tutorial 1](../core/media/tut1-dataflow.gif "Tut1_Dataflow")  
  
-   (El sistema de almacén envía una solicitud a una carpeta de archivos).  
  
-   Se configura una ubicación de recepción de BizTalk Server con el adaptador de archivos y una canalización de transmisión XML.  El adaptador de archivos sondea el archivo periódicamente desde la carpeta de archivos. Una vez recibido un mensaje, el motor de mensajería de BizTalk Server lleva el mensaje a través de una canalización.  Debido a que el mensaje de solicitud se encuentra en formato XML, en este caso se usa la canalización de transmisión XML.  La canalización de transmisión XML asegura de que el mensaje sea un archivo XML bien formado.  A continuación, el mensaje se guarda en la base de datos de cuadro de mensajes.  
  
-   Cuando el motor de orquestación observa que un mensaje está listo para ser procesado por una orquestación, crea una instancia de la orquestación.  En función del total general del mensaje, el motor de orquestaciones guarda un mensaje de solicitud o bien un mensaje de rechazo de solicitud en la base de datos de cuadro de mensajes.  
  
-   De nuevo, en función del mensaje de solicitud o del mensaje de rechazo de solicitud, el motor de mensajería usa el puerto de envío correspondiente para procesar el mensaje.  El motor de mensajería envía primero el mensaje por una canalización de transmisión XML y, a continuación, usa el adaptador de archivos para enviar el mensaje a diferentes carpetas de archivos según las configuraciones del puerto de envío.  
  
-   (Tanto el sistema de almacén como el monitor del sistema ERP han designado carpetas para recibir mensajes).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Antes de empezar el Tutorial](../core/before-you-begin-the-tutorial.md) 
  
-   [Lección 1: Definir los esquemas y un mapa](../core/lesson-1-define-schemas-and-a-map.md) 
  
-   [Lección 2: Definir el proceso empresarial](../core/lesson-2-define-the-business-process.md)  
  
-   [Lección 3: Implementar la solución](../core/lesson-3-deploy-the-solution.md)