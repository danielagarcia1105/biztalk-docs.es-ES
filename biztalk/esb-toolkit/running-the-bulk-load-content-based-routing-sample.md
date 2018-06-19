---
title: Ejecuta la mayor parte cargar muestra de enrutamiento basado en contenido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e981567-7c6c-4c13-bd5b-597efdd3fb50
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c5348563cc52c31b14dbceddf35bdb3d5d94cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294948"
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a>Ejecutar el masiva carga contenidos enrutamiento ejemplo
Esta parte del ejemplo muestra una cola con los mensajes que los ESB y Microsoft BizTalk enrutará a las colas de destino diferente según el nombre de cola especificado en cada mensaje de carga masiva. Usa las características de la muestra que ha visto en las dos partes anteriores.  
  
 **Para ejecutar el ejemplo de acceso de enrutamiento basado en contenido de carga masiva**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
2.  Ejecute la utilidad de IBM RfhUtil y, a continuación, seleccione el Administrador de cola denominado ESB. JMS. Sample.QueueManager en la primera lista desplegable para conectarse a este administrador de cola, como en la parte 2 de este ejemplo.  
  
3.  En la segunda lista desplegable, seleccione la cola de salida de destino denominada ESB. JMS. EJEMPLO. SENDTOBIZTALK, como en la parte 2 de este ejemplo.  
  
4.  Haga clic en el **carga preguntas** situado en la utilidad RfhUtil y, a continuación, navegue hasta el archivo de mensaje de prueba denominado 000128 de prueba. JMS ubicado en la subcarpeta denominada \Source\Samples\JMS\Test\Data\Load\\. Este archivo contiene un lote de 128 mensajes de prueba que el ejemplo enviará al ESB.  
  
5.  En el **carga** cuadro de diálogo, deje todos los valores se establecen en sus valores predeterminados.  
  
6.  En el **carga** cuadro de diálogo, haga clic en **Aceptar** para agregar todos los mensajes a la cola de entrada.  
  
7.  Después de un retraso mientras se ejecuta la aplicación, aparecen los mensajes de salida ESB en varias colas de destino, dependiendo de los valores en los encabezados JMS. Sin embargo, todos los especifican la misma cola responder a, por lo que todas las respuestas aparecen en ESB. JMS. EJEMPLO. Cola de respuesta. Abra el Explorador de la cola de WebSphere y examinar las colas para confirmarlo.