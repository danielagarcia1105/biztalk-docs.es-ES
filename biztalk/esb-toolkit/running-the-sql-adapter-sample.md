---
title: Ejecución del ejemplo de adaptador SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13566d08-7a59-4065-b0d7-19ae2765555e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505f60d287b82b5650855870329e9a18496d63f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979077"
---
# <a name="running-the-sql-adapter-sample"></a>Ejecución del ejemplo de adaptador SQL
El ejemplo de adaptador de SQL utiliza una aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de rampa de itinerario.  
  
 **Para ejecutar el ejemplo de adaptador de SQL**  
  
1. Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.  
  
2. En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3. Desactive el **usar el servicio de WCF** casilla de verificación para que se puede usar un itinerario del lado cliente.  
  
4. Seleccione el **dos servicios de manera** opción  
  
5. Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta de \Source\Samples\SqlAdapter \Itineraries.  
  
6. Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo OrderDoc.xml en la carpeta de \Source\Samples\SqlAdapter \Test.  
  
7. Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario.  
  
8. Asegúrese de que se inserta una fila en la tabla Product de la base de datos GlobalBankESB.  
  
   Para obtener información acerca de cómo funciona el ejemplo de adaptador de SQL, vea [SQL adaptador de ejemplo de funcionamiento](../esb-toolkit/how-the-sql-adapter-sample-works.md).