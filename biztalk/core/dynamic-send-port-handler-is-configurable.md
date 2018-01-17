---
title: "Controlador de puerto de envío dinámico es Configurable | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eb8f5ef-af95-4b2e-9a43-6f1240b25855
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11dffbe28d44d7665bc86ff0842c17ea01f7b3d3
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="dynamic-send-port-handler-is-configurable"></a>El controlador de puerto de envío dinámico es configurable
Al crear un puerto de envío dinámico, puede configurar un controlador de envío de adaptador para *cada* adaptador instalado. Considere el caso siguiente:  
  
 **Escenario**  
  
 Hay dos itinerarios de ESB en una aplicación. Itinerary1 usa un puerto de envío dinámico para enviar datos a un recurso compartido de archivo. Itinerary2 usa un puerto de envío dinámico para enviar correo electrónico. Anteriormente, los puertos de envío dinámicos se ejecutaban en el host predeterminado del adaptador. Itinerary1 está destinado a escenarios de bajo volumen de mensajes de gran tamaño. Itinerary2 está destinado a escenarios de alto volumen de mensajes de tamaño pequeño. Puesto que solo hay un host predeterminado para un adaptador, todos los mensajes se enrutan con el mismo host, lo que reduce el rendimiento.  
  
 **El cambio**  
  
 Para mejorar el rendimiento de los puertos de envío dinámico, puede configurarse un controlador de envío de adaptador para que use cualquier host. En el escenario de ESB, Itinerary1 usa HostA para enviar datos a un recurso compartido de archivos. Itinerary2 usa un puerto HostB para enviar correo electrónico.  
  
## <a name="select-a-send-handler"></a>Seleccione un controlador de envío  
 Al crear un puerto de envío unidireccional dinámico o un puerto de envío de petición-respuesta dinámico, el controlador de envío se puede configurar para usar cada adaptador instalado. Pasos:  
  
1.  En el **administración de BizTalk Server** de la consola, expanda **grupo de BizTalk [*GroupName*]**, expanda **aplicaciones**y, a continuación, expanda la aplicación que contendrá el puerto de envío.  
  
2.  Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, haga clic en **puerto de envío unidireccional dinámico** o **puerto de envío de petición-respuesta dinámico**.  
  
3.  En **propiedades**, haga clic en **configurar**.  
  
     Los adaptadores se mostrarán con el controlador de envío predeterminado. Haga clic en la flecha hacia abajo para seleccionar el host diferente.  
  
4.  Haga clic en **Aceptar** guardar la configuración.  
  
5.  De de baja y vuelva a inscribir el nuevo puerto de envío dinámico.  
  
6.  Reinicie la instancia de host original.  
  
7.  Reinicie la instancia de host nueva.  
  
 Entre las opciones de configuración adicionales del puerto de envío se incluyen:  
  
-   [Cómo configurar opciones avanzadas de transporte para un puerto de envío](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
-   [Cómo configurar opciones de copia de seguridad de transporte para un puerto de envío](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
-   [Cómo configurar asignaciones de salida para un puerto de envío](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
-   [Cómo configurar filtros para un puerto de envío](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
-   [Cómo asignar un certificado a un puerto de envío](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
-   [Cómo configurar el seguimiento de un puerto de envío](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
 Los distintos host se pueden ajustar. Los siguientes vínculos tratan la optimización de rendimiento:  
  
 [Optimizaciones generales de BizTalk Server](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
 [Administración de la configuración de rendimiento de BizTalk Server](http://go.microsoft.com/fwlink/p/?LinkId=267704)