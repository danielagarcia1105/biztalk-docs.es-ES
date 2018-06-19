---
title: Ejecutar el ejemplo de operaciones de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91d4e57-ba94-4730-8c5a-4c96902f313f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57480e6020b2ab262d7d9db522b9dd2f79aa49cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294540"
---
# <a name="running-the-biztalk-operations-sample"></a>Ejecutar el ejemplo de operaciones de BizTalk
El ejemplo de operaciones de Microsoft BizTalk utiliza una aplicación de cliente de prueba de Windows Forms para ejecutar métodos del servicio Web de las operaciones de BizTalk y mostrar los resultados. Puede abrir el proyecto de cliente de prueba para ejecutarlo y examinar el código para ver cómo puede usar el servicio Web de las operaciones de BizTalk en su propia arquitectura orientada a servicios (SOA) y aplicaciones de ESB.  
  
 En el Explorador de Windows, abra la carpeta denominada \Samples\BizTalkOperations\bin\Debug y, a continuación, ejecute la aplicación Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe.  
  
 La figura 1 muestra la aplicación de cliente de prueba para el servicio Web de las operaciones de BizTalk. Puede ejecutar todas las funciones del servicio Web de las operaciones de BizTalk con esta aplicación. La aplicación muestra los resultados en un formato de vista de árbol y muestra el mensaje devuelto por el servicio.  
  
 ![Prueba de servicio de Web](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")  
  
 **Figura 1**  
  
 **El cliente de prueba del servicio Web de BizTalk operaciones**  
  
 Para ejecutar un método del servicio Web de las operaciones de BizTalk que no requiere ningún parámetro, simplemente haga clic en el botón correspondiente en el lado izquierdo de la ventana de la aplicación. Para los métodos que requieren parámetros de entrada, seleccione el método en la lista desplegable en la parte superior de la ventana, escriba los valores de parámetro necesita y, a continuación, haga clic en el **invocar servicio** botón.  
  
## <a name="how-the-sample-works"></a>Cómo funciona el ejemplo  
 La aplicación de ejemplo crea una instancia del servicio Web de las operaciones de BizTalk ESB y llama al método adecuado según la configuración que seleccione en la aplicación. Pasa los valores que escriba en los controles de la aplicación como parámetros al método de servicio seleccionada y recopila la salida desde el método de servicio para mostrar en la ventana de la aplicación.