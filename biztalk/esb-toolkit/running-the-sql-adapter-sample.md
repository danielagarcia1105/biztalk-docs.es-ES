---
title: Ejecutar el ejemplo de adaptador SQL | Documentos de Microsoft
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
ms.openlocfilehash: bf04c06a1ef96974912ce3affe278d5a98936325
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294796"
---
# <a name="running-the-sql-adapter-sample"></a>Ejecutar el ejemplo de adaptador SQL
El ejemplo de adaptador de SQL utiliza una aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de itinerario en rampa.  
  
 **Para ejecutar el ejemplo de adaptador de SQL**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.  
  
2.  En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.  
  
3.  Desactive el **usar el servicio de WCF** casilla de verificación para que se puede utilizar un itinerario del lado cliente.  
  
4.  Seleccione el **dos servicios de manera** opción  
  
5.  Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta \Source\Samples\SqlAdapter \Itineraries.  
  
6.  Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo OrderDoc.xml en la carpeta \Source\Samples\SqlAdapter \Test.  
  
7.  Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa.  
  
8.  Asegúrese de que se inserta una fila en la tabla Product de la base de datos de GlobalBankESB.  
  
 Para obtener información sobre cómo funciona el ejemplo del adaptador de SQL, consulte [SQL adaptador de ejemplo de funcionamiento del](../esb-toolkit/how-the-sql-adapter-sample-works.md).