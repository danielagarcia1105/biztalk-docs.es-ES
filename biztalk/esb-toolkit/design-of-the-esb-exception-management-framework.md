---
title: Diseño del marco de administración de excepciones de ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfc2688c-c01c-4244-9e35-3d482135d8b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f25bec37d7ee6ec02db5db28e32ce8ed5b62f724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996581"
---
# <a name="design-of-the-esb-exception-management-framework"></a>Diseño del marco de administración de excepciones de ESB
Patrones coherentes y reutilizables para administrar las excepciones son una consideración principal de cualquier proyecto de desarrollo; ayudan a maximizar la facilidad de mantenimiento y que sea más fácil admitir la aplicación después de la implementación.  
  
 Una aplicación típica de BizTalk podría usar la características de mensajería de BizTalk, si lo desea iniciar una orquestación de procesamiento, llamar al motor de reglas de negocios, interactuar con varios sistemas (empresariales ERP) de planeamiento de recursos empresariales o con línea de negocio (LOB) y devolver un respuesta a un sistema independiente de otros fabricantes. Además, la ubicación en tiempo de ejecución de estos componentes, incluidos los subsistemas de BizTalk, puede residir en uno o más servidores distribuidos en todo el entorno actual. Esto es un escenario típico y requiere que el sistema para admitir detectar y notificar las excepciones que pueden producirse en cualquiera de los ESB o BizTalk desacoplan subsistemas o en los distintos sistemas LOB de terceros, cada uno de los cuales tiene sus propias restricciones de control de excepciones. Por ejemplo, el gran sistema puede rechazar un pedido enviado desde un sitio Web durante un ciclo de procesamiento normal; el sitio Web debe compensar este error y notificar al usuario.  
  
 Debido a su entorno y la complejidad de las aplicaciones de ESB, desarrollo de una solución coherente para la administración de excepciones de la aplicación debe representan los objetivos de diseño comunes siguientes:  
  
- Proporcionar un enfoque estandarizado para detectar y controlar las excepciones que se producen en el entorno de BizTalk Server (es decir, en los subsistemas de mensajería y orquestación).  
  
- Proporcionar patrones comunes que permiten a los procesos automatizados reaccionar ante y administrar las excepciones de aplicación.  
  
- Proporcionan un modelo de administración de excepciones de acoplamiento flexible que facilita la reutilización.  
  
- Proporcionan un mecanismo de notificación comunes para las excepciones de aplicación y sus Estados de mensajes disponibles que pueden aplicar a cualquier subsistema de BizTalk.  
  
  Para entender por qué la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona un mecanismo de error personalizado, es decir, el marco de administración de excepciones, y cómo funciona, es necesario comprender las características de administración de excepciones disponibles en BizTalk Server y por qué estas características no están totalmente capaz de satisfacer los objetivos de diseño anterior.  
  
## <a name="biztalk-server-exception-reporting"></a>Informes de excepción de servidor BizTalk Server  
 BizTalk Server es compatible con el siguiente control de excepciones y mecanismos de informes:  
  
- Enrutamiento de mensajes con errores  
  
- Consola de administración de BizTalk Server  
  
- Registro de eventos de Microsoft  
  
- Opciones de desarrollo personalizado  
  
  De forma predeterminada, las capacidades de BizTalk Server para controlar las excepciones dependen mucho intervención del operador. Por ejemplo, considere la situación donde un usuario envía un mensaje a BizTalk Server que se produce una excepción durante la fase de validación. De forma predeterminada, el mensaje se publica en la base de datos de cuadro de mensaje, donde se enruta a una cola de suspensión. Esto significa que un operador debe hacer lo siguiente:  
  
- Detectar independientemente de que se ha producido una excepción.  
  
- Guardar manualmente el mensaje con errores en el disco mediante la consola de administración de BizTalk Server.  
  
- Editar manualmente y corregir el mensaje y volver a enviarlo al sistema. En algunos casos, este proceso tiene la posibilidad de perder la información de contexto importante.  
  
  Para resolver estos problemas, BizTalk Server proporciona el mecanismo de enrutamiento de mensajes de error. Los desarrolladores y administradores pueden utilizarlo para crear los procesos de orquestación o mensajería puertos de envío configurados para suscribirse a las excepciones que se producen en el subsistema de mensajería. Esto proporciona una detección de errores automatizada y el mecanismo de enrutamiento que conserva el estado del mensaje original y se resuelve el problema de detección de excepciones.  
  
  Porque no se proporciona el enrutamiento automático de mensajes con errores para los procesos de orquestación, el desarrollador debe tener en cuenta si hay errores mediante la adición de bloques de controlador de excepción para formas de ámbito de la orquestación. Con esta solución, cada orquestación puede tener su propio control de excepciones, pero no hay ningún mecanismo para volver a usar la funcionalidad de control a través de varias orquestaciones de excepciones.  
  
  Esto significa que ahora hay dos formas muy distintas en el que las excepciones de mensajería se procesan y administran en un sistema de BizTalk Server y en qué orquestación se procesan las excepciones de otra forma. Por lo tanto, los desarrolladores deben personalizar el mecanismo para que se adapte a sus propios requisitos si desean implementar un sistema que cumpla los requisitos descritos anteriormente en esta sección de control de excepciones.  
  
## <a name="biztalk-server-administration-console"></a>Consola de administración de BizTalk Server  
 La consola de administración de BizTalk Server proporciona un conjunto de páginas de información general del grupo, contemplada como el concentrador de grupo de BizTalk. Con estas páginas, los administradores pueden consultar los mensajes suspendidos y excepciones agrupadas por aplicación, nombre de servicio, código de error o URI, como se muestra en la figura 1.  
  
 ![Consola de administración](../esb-toolkit/media/ch4-adminconsole.gif "Ch4-AdminConsole")  
  
 **Figura 1**  
  
 **Las páginas de información general de grupo de BizTalk Server Administration Console**  
  
 Aunque la característica de información general de grupo proporciona una interfaz de usuario común para ver las excepciones, las vistas se limitan a las instancias de servicio "live". Examinar el estado puede ser una tarea compleja porque los administradores deben explorar en profundidad del árbol para cada elemento. Además, otros factores limitan las capacidades de la consola de administración de BizTalk Server como una herramienta de informes de excepción de aplicación:  
  
- No hay ninguna funcionalidad para los datos de inteligencia empresarial de minería de datos. Por ejemplo, no se puede consultar para las aplicaciones de peor infractor mensualmente o examinar tendencias trimestrales para las excepciones de aplicación.  
  
- Las empresas pueden requerir las alertas que se genera cuando se producen ciertas excepciones de aplicación o al alcanzar umbrales específicos, pero hay una funcionalidad para suscribirse a estos tipos de eventos de excepción.  
  
- Microsoft Management Console (MMC) que usa la consola de administración como la interfaz de usuario mecanismo (interfaz de usuario) no es una interfaz ideal, y no siempre es conveniente tener acceso en entornos de producción. Como mínimo, requiere que los usuarios sean miembros del rol operadores de BizTalk; y, en entornos de producción, acceso a la consola MMC normalmente solo es posible a través de Terminal Server.  
  
- La consola muestra solo (instancias de servicio suspendidas) de las excepciones no controladas. Si el desarrollador controla la excepción en la orquestación, lo que permite la orquestación puede finalizar naturalmente, la información de excepción nunca aparecerá en la consola de administración.  
  
  El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] trata estas limitaciones mediante el mecanismo de excepción enrutamiento de orquestación de error de ESB. Esto parece el mecanismo de enrutamiento de mensajes de error de servidor BizTalk Server. Además, el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye un componente de canalización en un puerto de envío se suscribe a mensajes generados desde el mecanismo de excepción enrutamiento de orquestación de error de ESB y el mecanismo de enrutamiento de mensajes de error y normaliza a ellos.  
  
  El marco de administración de excepciones de ESB aprovecha de otras características de BizTalk Server, como el modelo de suscripción y basado en eventos actividad de supervisión económica (BAM). Esto significa que el marco de administración de excepciones de ESB puede realizar un seguimiento de los puntos de datos de excepción con BAM y, a continuación, publicarlos en el Portal de BAM de BizTalk para la supervisión.