---
title: Acerca de los itinerarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d34632f-8652-49dd-97b7-2513aacc1bd7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd41dcfc1c5b6a090d48411956b19986aa2d676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001093"
---
# <a name="about-itineraries"></a>Acerca de los itinerarios
Un itinerario es una representación de una directiva de mediación de ESB para ejecutar una secuencia de procesamiento de instrucciones basadas en la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] formato extensible. Un itinerario puede verse como un lenguaje de mediación de alto nivel que describe una secuencia de los servicios de itinerario declarativas que están asociados con los componentes de mediación mediante la configuración de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] motor principal. Puede diseñar flujos de mediación para describir cómo se deben procesar los mensajes, y puede organizar el flujo completo como un dibujo visual. En tiempo de ejecución, el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] motor principal ejecuta el itinerario generado por el Diseñador de itinerario.  
  
## <a name="the-itinerary-designer-surface"></a>La superficie del Diseñador de itinerarios  
 La superficie del Diseñador de itinerarios es un diseñador visual que se usa para crear [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerarios y exportar estas itinerarios en formato de tiempo de ejecución. Es un lienzo al que puede arrastrar elementos desde el cuadro de herramientas, como se muestra en la figura 1.  
  
 ![Diseñador de itinerarios](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5-ItineraryDesigner")  
  
 **Figura 1**  
  
 **Superficie del Diseñador de itinerarios**  
  
 El nombre del itinerario se muestra en la pestaña superior del Diseñador de itinerario y en la barra de título de Microsoft Visual Studio. La superficie de diseño es una sola área y contiene los elementos del modelo que describen el flujo de mensajes real de los itinerarios. El ItineraryDSL le permite modificar las propiedades del elemento de modelo mediante la ventana Propiedades de Visual Studio.  
  
## <a name="itinerary-designer-toolbox"></a>Cuadro de herramientas Diseñador de itinerario  
 El cuadro de herramientas de Visual Studio contiene fichas, que representan conjuntos de herramientas. Al abrir un proyecto de Visual Studio que usa el Diseñador de itinerario, el cuadro de herramientas contiene dos pestañas: el **General** ficha y el **ItineraryDsl** pestañas. El **ItineraryDsl** ficha contiene las siguientes herramientas:  
  
-   **Herramienta de servicio de itinerarios**. Este elemento de modelo se corresponde con el servicio de itinerarios de mediación y representa una instrucción de procesamiento.  
  
-   **Herramienta conector**. Este elemento de modelo define la relación entre los elementos de modelo individuales de la superficie del Diseñador de itinerario.  
  
-   **Herramienta de fuera de rampa**. Este elemento de modelo corresponde a la fuera de rampa que envía un mensaje. El Diseñador de itinerario permite varios rampas por modelo.  
  
-   **Herramienta de rampa de**. Este elemento de modelo corresponde a una vía rápida que recibe un mensaje. El Diseñador de itinerario permite solo una vía rápida por modelo.  
  
-   **Herramienta de Service Broker itinerario**. Este elemento de modelo corresponde al servicio de itinerarios mediación que permite el flujo de mensajes definido con varias entradas y salidas múltiples.  
  
-   **Puerto de salida de Broker itinerario**. Este elemento de modelo corresponde al puerto de salida único del servicio de agente de itinerario. El elemento de modelo de itinerario de Service Broker permite a varios puertos de salida.  
  
## <a name="steps-in-itinerary-development"></a>Pasos en el desarrollo de itinerarios  
 Para desarrollar un itinerario, que representa el flujo de mediación de ESB, normalmente debe realizar las siguientes acciones:  
  
- Agregar elementos de modelo para representar el mensaje de procesamiento de los pasos para su itinerario. El Diseñador de itinerario proporciona un cuadro de herramientas que contiene formas que se utilizan para representar diferentes acciones o abstracciones clave.  
  
- Especifique las propiedades del modelo de itinerarios, que incluyen una cadena de conexión a la configuración de exportador de base de datos y el modelo de administración de Microsoft BizTalk Server.  
  
- Los elementos del modelo de vía rápida y fuera de rampa de enlace a BizTalk físico ubicaciones de recepción y puertos de envío mediante la asociación de estos elementos de modelo con extensores de tecnología correspondiente.  
  
- Asociar elementos de modelo de servicios de itinerario extensores y definir propiedades de tecnologías específicas requeridas un objeto extender. Estas propiedades pueden variar de un tipo determinado del extensor; pueden representar las propiedades del servicio de itinerarios de mediación y propiedades específicas de BizTalk asociadas con sus componentes de tiempo de ejecución y los artefactos.  
  
- Identificar los componentes personalizados que desea hacer referencia como servicios de mediación de itinerarios. Por ejemplo, puede desarrollar una orquestación como servicio de itinerarios.  
  
- Compruebe la configuración de elemento de modelo de resolución frente a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuración en tiempo de ejecución mediante la invocación de servicio de resolución de la superficie del diseñador.  
  
- Validar y exportar la directiva de tiempo de ejecución itinerario mediante un exportador. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona dos exportadores con el Diseñador de itinerario: exportador y exportador de la base de datos de archivos. Como alternativa, puede implementar un exportador personalizado.  
  
- Pruebe su itinerario mediante BizUnit framework o aplicaciones de cliente de prueba.  
  
## <a name="security-considerations-for-developing-itineraries"></a>Consideraciones de seguridad para el desarrollo de itinerarios  
 Al diseñar los itinerarios, debe considerar los posibles problemas de seguridad:  
  
-   Evite la especificación de credenciales de usuario sin usar un certificado de las propiedades del modelo.  
  
-   ¿Se refieren a BizTalk puertos de recepción con ubicaciones de recepción que permiten el acceso anónimo.  
  
-   Proteja el canal de transporte o mensaje si el mensaje de itinerarios contiene datos confidenciales.  
  
-   Proteger los mensajes en el cuadro de mensaje con un componente de canalización si los mensajes contienen datos confidenciales que necesita ser protegido mientras están en tránsito.