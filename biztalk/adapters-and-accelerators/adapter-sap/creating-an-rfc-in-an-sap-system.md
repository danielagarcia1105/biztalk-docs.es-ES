---
title: "Información general de creación de una solicitud de cambio en una SAP para utilizar con el adaptador SAP en BizTalk | Documentos de Microsoft"
description: "Crear una solicitud de cambio, RFC destino y envíe una solicitud de cambio de sistema SAP: módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35937183-fc1e-49cd-8a75-8f62effe0013
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802a2e33b8bc902dc784276ce7c1d9c3f37f3b12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-and-send-an-rfc-in-sap"></a>Crear y enviar una solicitud de cambio en SAP
Enumera las tareas de alto nivel que se complete en el sistema SAP para crear una solicitud de cambio. Cada tarea puede implicar procedimientos muy detallados. Como resultado, se recomienda ponerse en contacto con el Administrador de SAP para completar estas tareas, o consulte la Guía de SAP.  
  
## <a name="create-an-rfc"></a>Crear una solicitud de cambio  
  
1.  Inicie la GUI de SAP.  
  
2.  Vaya a la transacción SE37 (generador de función), escriba el nombre RFC y haga clic en **crear**.  
  
3.  Escriba un función grupo existente en la que se creará la solicitud de cambio, una descripción breve de la solicitud de cambio y haga clic en **guardar**.  
  
4.  En el **atributos** ficha, seleccione la **Remote-Enabled módulo** botón de radio.  
  
5.  En el **importar** ficha, especifique los parámetros de importación. Estos parámetros se utilizan para pasar los datos externos para el módulo de función.  
  
6.  En el **exportar** ficha, especifique los parámetros de exportación.  
  
7.  En el **Changing** ficha, especifique los parámetros de la variables.  
  
8.  En el **tablas** ficha, escriba los nombres de tabla.  
  
9. En el **excepciones** ficha, escriba las excepciones para controlar los errores.  
  
10. En el **código fuente** ficha, escriba el código fuente (lógica) para la solicitud de cambio.  
  
11. Haga clic en el **activar** icono en la barra de herramientas para activar el módulo de función.  

## <a name="create-an-rfc-destination"></a>Crear un destino RFC  
  
1.  Inicie la GUI de SAP.  
  
2.  Vaya a SM59 de transacciones (mostrar y mantener destinos RFC).  
  
3.  En la barra de menús, haga clic en **crear**.  
  
4.  Escriba el destino RFC, el tipo de conexión, la descripción y, a continuación, presione ENTRAR.  
  
5.  Seleccione el **programa de servidor registrado** botón de opción, escriba el Id. de programa, el host de puerta de enlace y el servicio de puerta de enlace.  
  
6.  Guarde el destino RFC.  

## <a name="send-an-rfc-from-an-sap-system"></a>Enviar una solicitud de cambio de un sistema SAP  
  
1.  Inicie la GUI de SAP.  
  
2.  Crear un sistema lógico con la transacción de BD54.  
  
3.  Crear un destino RFC en conexiones de TCP/IP con la transacción SM59.  
  
4.  Crear un puerto mediante transacciones WE21 y adjuntarlo al destino RFC creado en el último paso.  
  
5.  Desencadenar una solicitud de cambio mediante SE37. Este RFC debe contener la lógica para realizar una solicitud de cambio de llamar a una aplicación externa y, a continuación, recibir una respuesta de esa aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Realizar tareas mediante la GUI de SAP para escenarios de adaptadores SAP específicos](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)