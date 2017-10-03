---
title: Acerca de itinerarios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d34632f-8652-49dd-97b7-2513aacc1bd7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9a759a6afdd55c3c1646d02c480aa193261aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-itineraries"></a>Acerca de itinerarios
Un itinerario es una representación de una directiva de mediación de ESB para ejecutar una secuencia de procesamiento de instrucciones según el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] formato extensible. Un itinerario puede verse como un lenguaje de alto nivel de mediación que describe una secuencia de servicios itinerarios declarativas que están asociados a componentes de mediación por la configuración de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] motor principal. Puede diseñar flujos de mediación para describir cómo se deben procesar los mensajes, y puede organizar el flujo completo como un dibujo visual. En tiempo de ejecución, el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] motor principal ejecuta el itinerario generado por el Diseñador de itinerario.  
  
## <a name="the-itinerary-designer-surface"></a>La superficie del Diseñador de itinerarios  
 La superficie del Diseñador de itinerario es un diseñador visual que se utiliza para crear [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerarios y exportar estos itinerarios en formato de tiempo de ejecución. Es un lienzo en el que puede arrastrar elementos desde el cuadro de herramientas, como se muestra en la figura 1.  
  
 ![Diseñador de itinerarios](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5-ItineraryDesigner")  
  
 **Figura 1**  
  
 **Superficie del Diseñador de itinerarios**  
  
 El nombre de la itinerario se muestra en la pestaña superior del Diseñador de itinerario y en la barra de título de Microsoft Visual Studio. La superficie de diseño es un área única y contiene elementos del modelo que describen el flujo de mensajes real de la itinerario. El ItineraryDSL le permite modificar las propiedades del elemento de modelo mediante la ventana Propiedades de Visual Studio.  
  
## <a name="itinerary-designer-toolbox"></a>Cuadro de herramientas Diseñador de itinerario  
 El cuadro de herramientas de Visual Studio contiene fichas, que representan los conjuntos de herramientas. Al abrir un proyecto de Visual Studio que usa el Diseñador de itinerario, el cuadro de herramientas contiene dos pestañas: el **General** ficha y **ItineraryDsl** pestañas. El **ItineraryDsl** pestaña contiene las siguientes herramientas:  
  
-   **Herramienta de servicio itinerario**. Este elemento de modelo se corresponde con el servicio de mediación itinerarios y representa una instrucción de procesamiento.  
  
-   **Herramienta conector**. Este elemento de modelo define la relación entre elementos de modelo individuales en la superficie del Diseñador de itinerario.  
  
-   **Herramienta de fuera de rampa**. Este elemento de modelo corresponde a la fuera de rampa que envía un mensaje. El Diseñador de itinerario permite varios desactivar pendientes por cada modelo.  
  
-   **Herramienta de en rampa**. Este elemento de modelo corresponde a en rampa que recibe un mensaje. El Diseñador de itinerario permite solo una en rampa por modelo.  
  
-   **Herramienta de Service Broker itinerario**. Este elemento de modelo corresponde al servicio de mediación itinerarios que permite el flujo de mensajes definidos con varias entradas y salidas múltiples.  
  
-   **Puerto de salida de Broker itinerario**. Este elemento de modelo correspondiente al puerto de salida única del servicio de agente de itinerario. El elemento de modelo de itinerario de Service Broker permite a varios puertos de salida.  
  
## <a name="steps-in-itinerary-development"></a>Pasos de desarrollo itinerario  
 Para desarrollar un itinerario, que representa el flujo de mediación de ESB, normalmente debe realizar las siguientes acciones:  
  
-   Agregar elementos de modelo para representar lo pasos para su itinerario de procesamiento de mensajes. El Diseñador de itinerario proporciona un cuadro de herramientas que contiene formas utilizadas para representar diferentes acciones o abstracciones de clave.  
  
-   Especificar propiedades del modelo itinerarios, que incluyen una cadena de conexión a la configuración de exportador de base de datos y el modelo de administración de Microsoft BizTalk Server.  
  
-   Elementos de modelo en rampa y fuera de rampa de enlace a BizTalk físico ubicaciones de recepción y puertos de envío mediante la asociación de estos elementos de modelo con extensores de tecnología correspondiente.  
  
-   Asociar elementos de modelo de servicios itinerarios extensores y definir propiedades específicas de la tecnología requeridos por un dispositivo extender. Estas propiedades pueden variar de un tipo determinado del extensor; pueden representar propiedades del servicio de mediación itinerarios y propiedades específicas de BizTalk asociados con sus componentes en tiempo de ejecución y artefactos.  
  
-   Identifique los componentes personalizados que desea hacer referencia como servicios de mediación itinerarios. Por ejemplo, puede desarrollar una orquestación como servicio de itinerarios.  
  
-   Compruebe la configuración de elemento de modelo de resolución contra [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración de tiempo de ejecución mediante la invocación de servicio de la resolución de la superficie del diseñador.  
  
-   Validar y exportar la directiva de tiempo de ejecución itinerario mediante un exportador. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona dos exportadores con el Diseñador de itinerario: exportador y exportador de la base de datos de archivos. Como alternativa, puede implementar un exportador personalizado.  
  
-   Probar su itinerario usando BizUnit framework o aplicaciones de cliente de prueba.  
  
## <a name="security-considerations-for-developing-itineraries"></a>Consideraciones de seguridad para desarrollar itinerarios  
 Cuando diseña itinerarios, debe tener en cuenta posibles problemas de seguridad:  
  
-   Evite especificar credenciales de usuario sin usar un certificado de las propiedades del modelo.  
  
-   ¿Se refieren a BizTalk puertos de recepción con ubicaciones de recepción que permiten el acceso anónimo.  
  
-   Proteja el canal de transporte o mensaje si el mensaje itinerario contiene datos confidenciales.  
  
-   Proteger los mensajes en el cuadro de mensaje con un componente de canalización si los mensajes contienen datos confidenciales que necesitan ser protegido mientras están en tránsito.