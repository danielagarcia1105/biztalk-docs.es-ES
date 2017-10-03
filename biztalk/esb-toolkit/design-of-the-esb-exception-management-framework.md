---
title: "Diseño de la estructura de administración de la excepción de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfc2688c-c01c-4244-9e35-3d482135d8b7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c9bf8691701aa9fba8060865fcd3cb5abfba06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="design-of-the-esb-exception-management-framework"></a>Diseño de la estructura de administración de la excepción de ESB
Patrones coherentes y reutilizables para administrar las excepciones son una consideración principal de cualquier proyecto de desarrollo; ayudan a maximizar la facilidad de mantenimiento y facilitan la compatibilidad con la aplicación después de la implementación.  
  
 Una aplicación típica de BizTalk podría usar la características de mensajería de BizTalk, si lo desea iniciar el procesamiento de una orquestación, llama el motor de reglas de negocios, interactuar con varios línea de negocio (LOB) o sistemas (empresariales ERP) de planificación de recursos empresariales y devolver un respuesta a un sistema independiente de otros fabricantes. Además, la ubicación de tiempo de ejecución de estos componentes, incluidos los subsistemas de BizTalk, puede residir en uno o más servidores distribuidos en todo el entorno actual. Este es un escenario típico y requiere el sistema para admitir detectar y notificar las excepciones que pueden producirse en cualquiera de los ESB o BizTalk desacoplan subsistemas o en los distintos sistemas LOB de terceros, cada uno de los cuales tiene su propio restricciones de control de excepciones. Por ejemplo, los clientes de mainframe pueden rechazar un pedido enviado desde un sitio Web durante un ciclo de procesamiento normal; el sitio Web debe compensar este error y notificar al usuario.  
  
 Debido a su entorno y la complejidad de las aplicaciones de ESB, desarrollo de una solución coherente de administración de excepciones de aplicación debe representan los objetivos de diseño comunes siguientes:  
  
-   Proporcionan un método estandarizado para detectar y controlar las excepciones que se producen en el entorno de BizTalk Server (es decir, en los subsistemas de mensajería y orquestación).  
  
-   Proporcionar patrones comunes que permiten a los procesos automatizados reaccionar ante y administrar las excepciones de aplicación.  
  
-   Proporcionan un modelo de administración de excepciones de acoplamiento flexible que facilita la reutilización.  
  
-   Proporcionar un mecanismo de notificación comunes para las excepciones de aplicación y sus Estados de mensajes disponibles que pueden aplicar a cualquier subsistema de BizTalk.  
  
 Para entender por qué la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona un mecanismo de error personalizado, es decir, el marco de trabajo de administración de excepciones y cómo funciona, es necesario conocer las características de administración de excepciones disponibles en BizTalk Server y por qué estas características no están totalmente capaz de satisfacer los objetivos de diseño anterior.  
  
## <a name="biztalk-server-exception-reporting"></a>Informes de excepción de servidor BizTalk Server  
 BizTalk Server es compatible con la siguiente excepción gestión y los mecanismos de informes:  
  
-   Enrutamiento de mensajes con errores  
  
-   Consola de administración de BizTalk Server  
  
-   Registro de eventos de Microsoft  
  
-   Opciones de desarrollo personalizado  
  
 De forma predeterminada, las capacidades de BizTalk Server para controlar las excepciones dependen de un gran ahorro intervención del operador. Por ejemplo, considere la situación donde un usuario envía un mensaje a BizTalk Server que se produce una excepción durante la fase de validación. De forma predeterminada, el mensaje se publica en la base de datos de cuadro de mensaje donde se enruta a una cola de suspensión. Esto significa que un operador debe hacer lo siguiente:  
  
-   Detectar independientemente de que se produjo una excepción.  
  
-   Guardar de forma manual el mensaje con errores en el disco mediante el [!INCLUDE[prague](../includes/prague-md.md)] consola de administración.  
  
-   Manualmente editar y corregir el mensaje y volver a enviarla al sistema. En algunos casos, este proceso tiene el potencial de pérdida de información de contexto importante.  
  
 Para resolver estos problemas, [!INCLUDE[prague](../includes/prague-md.md)] proporciona el mecanismo de enrutamiento de mensajes de error. Los desarrolladores y administradores pueden utilizar esto para crear procesos de orquestación o mensajería puertos de envío configurados para suscribirse a las excepciones que aparecen en el subsistema de mensajería. Esto proporciona una detección de errores automatizada y el mecanismo de enrutamiento que conserva el estado del mensaje original y se resuelve el problema de detectar las excepciones.  
  
 Porque no se proporciona el enrutamiento automático de mensajes error para los procesos de orquestación, el desarrollador debe tener en cuenta si hay errores mediante la adición de bloques de controlador de excepción para formas de ámbito de la orquestación. Con esta solución, cada orquestación puede tener su propio control de excepciones, pero no hay ningún mecanismo para volver a usar la funcionalidad de control a través de varias orquestaciones de excepciones.  
  
 Esto significa que ahora hay dos maneras muy diferentes en el que las excepciones de mensajes se procesan y administran en un sistema de BizTalk Server y una tercera forma de en qué orquestación se procesan las excepciones. Por lo tanto, los desarrolladores deben personalizar el mecanismo para satisfacer sus propias necesidades si van a implementar un sistema que cumple los requisitos descritos anteriormente en esta sección de control de excepciones.  
  
## <a name="biztalk-server-administration-console"></a>Consola de administración de BizTalk Server  
 El [!INCLUDE[prague](../includes/prague-md.md)] consola de administración proporciona un conjunto de páginas de información general del grupo, denominados el concentrador de grupo de BizTalk. Con estas páginas, los administradores para consultar mensajes suspendidos y excepciones agrupadas por aplicación, el nombre del servicio, el código de error o el URI, como se muestra en la figura 1.  
  
 ![Consola de administración de](../esb-toolkit/media/ch4-adminconsole.gif "Ch4-AdminConsole")  
  
 **Figura 1**  
  
 **El [!INCLUDE[prague](../includes/prague-md.md)] páginas de información general sobre el grupo de consola de administración**  
  
 Aunque la característica de información general de grupo proporciona una interfaz de usuario común para ver las excepciones, las vistas se limitan a "live" instancias de servicio. Examinar el estado puede ser una tarea compleja, dado que los administradores deben explorar en profundidad del árbol para cada elemento. Además, otros factores limitan las capacidades de la consola de administración de BizTalk Server como una herramienta de informes de excepción de aplicación:  
  
-   No hay ninguna capacidad de los datos de business intelligence de minería de datos. Por ejemplo, no se puede consultar para las aplicaciones peor infractor mensualmente o examinar trimestrales tendencias para las excepciones de aplicación.  
  
-   La empresa puede requerir las alertas que se genera cuando se producen ciertas excepciones de aplicación o al alcanzar umbrales específicos, pero no es posible suscribirse a estos tipos de eventos de excepción.  
  
-   Microsoft Management Console (MMC) que usa la consola de administración como la interfaz de usuario mecanismo (interfaz de usuario) no es una interfaz ideal, y no siempre es conveniente tener acceso en entornos de producción. Como mínimo, requiere que los usuarios sean miembros del rol operadores de BizTalk; y, en entornos de producción, acceso a la consola MMC normalmente solo es posible a través de Terminal Server.  
  
-   La consola muestra únicamente (instancias de servicio suspendidas) de las excepciones no controladas. Si el desarrollador controla la excepción en la orquestación, lo que permite la orquestación finalizar con normalidad, la información de excepción nunca aparecerá en la consola de administración.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] soluciona estas limitaciones mediante el mecanismo de excepción enrutamiento de orquestación de error de ESB. Esto se asemeja mucho el mecanismo de enrutamiento de mensajes de error de [!INCLUDE[prague](../includes/prague-md.md)]. Además, la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye un componente de canalización en un puerto de envío que se suscribe a los mensajes generados desde el mecanismo de excepción enrutamiento de orquestación de error de ESB y el mecanismo de enrutamiento de mensajes de error y normaliza ellos.  
  
 El marco de trabajo de administración de excepciones de ESB aprovecha las ventajas de otras características de BizTalk Server, como el modelo de suscripción y basado en eventos actividad supervisión económica (BAM). Esto significa que el marco de trabajo de administración de excepciones de ESB puede realizar un seguimiento de los puntos de datos de excepción con BAM y, a continuación, publicarlos en el Portal de BAM de BizTalk para la supervisión.