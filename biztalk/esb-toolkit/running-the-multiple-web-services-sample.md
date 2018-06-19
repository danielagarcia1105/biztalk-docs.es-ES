---
title: Ejecuta la Web de varios servicios de ejemplo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b201c7c3-213a-4009-8872-5a4c1cbb8195
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ec54fabb7ed140fd88b5a2d5a07d788805c741e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294804"
---
# <a name="running-the-multiple-web-services-sample"></a>Ejecutar el ejemplo de servicios Web varios
El ejemplo de varios servicios Web usa la aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de itinerario en rampa.  
  
 **Para ejecutar el ejemplo de varios servicios Web**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.  
  
2.  En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3.  Desactive el **usar el servicio de WCF** casilla, por lo que puede utilizarse un itinerario del lado cliente.  
  
4.  Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta \Source\Samples\MultipleWebServices\Itineraries.  
  
5.  Seleccione el **dos servicios de manera** casilla de verificación para la aplicación realizará un itinerario bidireccional de servicios de operación.  
  
6.  Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.  
  
7.  Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa. Espere a que un mensaje de respuesta que aparezcan en el **resultado** cuadro.  
  
 Para obtener información acerca de cómo el ejemplo de varios servicios Web usa el servicio de itinerario de ESB, consulte [cómo varios Web Services funciona el ejemplo](../esb-toolkit/how-the-multiple-web-services-sample-works.md).