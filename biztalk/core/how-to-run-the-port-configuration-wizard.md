---
title: Cómo ejecutar el Asistente para configuración de puertos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Port Configuration Wizard [Orchestration Designer], starting
- Port Configuration Wizard [Orchestration Designer], how to
- Port Configuration Wizard [Orchestration Designer], about Port Configuration Wizard
- ports, Port Configuration Wizard [Orchestration Designer]
- Port Configuration Wizard [Orchestration Designer]
ms.assetid: 8035ce32-5ed4-49cb-b6f0-998b0460751e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbdb5843eb8011478f13c0de6443bb1ded177378
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255796"
---
# <a name="how-to-run-the-port-configuration-wizard"></a>Cómo ejecutar el Asistente para configuración de puertos
Utilice el Asistente para configuración de puertos para crear y configurar un puerto en el Diseñador de orquestaciones. Un puerto debe tener asociado un tipo de puerto. Use el Asistente para seleccionar un tipo de puerto existente o para crear un nuevo tipo de puerto. Para obtener más información sobre los puertos y tipos de puertos, consulte [mediante puertos en orquestaciones](../core/using-ports-in-orchestrations.md).  
  
### <a name="to-start-the-wizard"></a>Para iniciar el Asistente  
  
1.  Con el botón secundario de un puerto (en la superficie de diseño o en la ventana Vista orquestación) y haga clic en **Configurar puerto**.  
  
2.  Ejecute elementos de etiqueta inteligente cuyas acciones asociadas hagan que se cree un puerto.  
  
3.  Al seleccionar la **nuevo parámetro de puerto configurado** comando en el menú contextual de la carpeta parámetros de orquestación en la ventana Vista orquestación.  
  
### <a name="to-run-the-wizard"></a>Para ejecutar el Asistente  
  
1.  Abra el Asistente para configuración de puertos.  
  
2.  Especifique la información del puerto. Para ayudarle, el Asistente muestra varias páginas. Después de completar cada página, mover a la siguiente, haga clic en **siguiente**, o mover a la anterior, haga clic en **volver**.  
  
    -   **Propiedades de puerto**. Escriba un nombre para el puerto.  
  
    -   **Seleccione un tipo de puerto.** En esta página, primero debe selecciona si desea que un **nuevo tipo de puerto** o un **tipo de puerto existente**. Si selecciona **tipo de puerto existente**, a continuación, usar un control de árbol para elegir qué tipo de puerto existente para asignar.  
  
         Si selecciona **nuevo tipo de puerto**, a continuación, debe escribir el nombre del tipo de puerto en el **nombre** texto cuadro, o bien acepte el nombre predeterminado sugerido. Seleccione también el patrón de comunicación del tipo de puerto (unidireccional o solicitud-respuesta), así como cualquier restricción de acceso que deba imponerse en el nuevo tipo de puerto.  
  
    -   **Enlace de puerto**. En esta página Especifique la dirección de comunicación, también conocido como el *polaridad*y el tipo de enlace del puerto.  
  
         La opción de polaridad que seleccione depende en parte en el patrón de comunicación del tipo de puerto que seleccionó en la página anterior del asistente, **seleccionar un tipo de puerto**. Las opciones disponibles se resumen en la siguiente tabla:  
  
        |Dirección de puerto|Patrón de comunicación|Dirección de comunicación que puede elegir en la página Enlace de puerto|  
        |--------------------|---------------------------|---------------------------------------------------------------|  
        |Send|Unidireccional|Siempre enviaré los mensajes en este puerto.|  
        |Receive|Unidireccional|Siempre recibiré los mensajes en este puerto.|  
        |Envío-Recepción|Petición-respuesta|Enviar una solicitud y recibiré una respuesta.|  
        |Recepción-Envío|Solicitud-respuesta|Recibiré una solicitud y enviaré una respuesta.|  
  
         Tiene la opción de cuatro tipos de enlace diferentes: especificar más tarde, especificar ahora, dinámico y directo. Cada opción muestra un conjunto distinto de opciones de configuración, tal y como se resume a continuación:  
  
         **Especificar más tarde.** después de seleccionar esta opción, no tiene que elegir opciones adicionales de configuración en el Asistente porque la información de enlace no se determina en tiempo de diseño. Esta información la agrega normalmente un administrador en tiempo de implementación.  
  
         **Especificar ahora.** puede especificar en tiempo de diseño un URI que defina la entidad a la que se va a enlazar el puerto. También debe seleccionar uno de los valores de una lista de tipos de transporte que incluye opciones como Message Queue Server de BizTalk, ARCHIVO, SMTP, HTTP y SOAP. Se trata de una lista codificada con el fin de realizar previamente enlaces en el Diseñador de orquestaciones; por tanto, en esta lista no están disponibles otros transportes. Por último, seleccione una canalización de recepción y una canalización de envío en la lista de canalizaciones disponibles. La lista de cada uno de ellos incluye todas las canalizaciones en el proyecto actual más la opción de seleccionar una canalización desde un ensamblado de referencia, que muestra la **Seleccionar tipo de artefacto** cuadro de diálogo.  
  
         **Dinámica.** Esta opción tiene opciones similares a **especificar ahora**, pero está disponible solo para un puerto de envío. Le permite especificar la canalización de envío que va a utilizar. Puede especificar el puerto por separado en un **expresión** forma para que se asigna en tiempo de ejecución.  
  
         **Directa.** en el caso de enlace directo, puede seleccionar un puerto al que conectarse de modo que el enrutamiento se base en las expresiones de filtro de los mensajes entrantes en la base de datos de cuadro de mensajes o de modo que sea un puerto de autocorrelación. Puede seleccionar un puerto en el cuadro de lista desplegable.  
  
         Para obtener más información, consulte [enlaces de puerto](../core/port-bindings.md).  
  
3.  Finalice el asistente. La página final del Asistente para configuración de puertos, titulada " **completar el Asistente para puertos**, muestra las selecciones realizadas en las páginas anteriores que permitan comprobar antes de confirmar los cambios. Si los cambios son correctos, haga clic en **finalizar**. En caso contrario, haga clic en **volver** para volver a escribir toda la información que desea cambiar. A continuación, desplazarse por el Asistente para nuevo y haga clic en **finalizar** cuando la información que se muestra en la página final coincida con los cambios que desee realizar.  
  
    > [!NOTE]
    >  Si va a crear un nuevo puerto y hace clic en **cancelar** en el Asistente en cualquier momento antes de la configuración del puerto de finalización, no se crea el puerto. Si utiliza el Asistente para modificar un puerto existente y cancela el Asistente, se desharán los cambios que haya realizado. En caso contrario, si hace clic en **cancelar** en el asistente, el adaptador se creará, pero no se establecen sus propiedades. Puede establecer manualmente las propiedades del puerto en la ventana Propiedades del puerto o volver a ejecutar el Asistente.  
  
## <a name="see-also"></a>Vea también  
 [Uso de puertos en orquestaciones](../core/using-ports-in-orchestrations.md)