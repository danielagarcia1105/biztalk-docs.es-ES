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
# <a name="running-the-sql-adapter-sample"></a><span data-ttu-id="d60a3-102">Ejecución del ejemplo de adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="d60a3-102">Running the SQL Adapter Sample</span></span>
<span data-ttu-id="d60a3-103">El ejemplo de adaptador de SQL utiliza una aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="d60a3-103">The SQL Adapter sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="d60a3-104">**Para ejecutar el ejemplo de adaptador de SQL**</span><span class="sxs-lookup"><span data-stu-id="d60a3-104">**To run the SQL Adapter sample**</span></span>  
  
1. <span data-ttu-id="d60a3-105">Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="d60a3-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="d60a3-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="d60a3-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="d60a3-107">Desactive el **usar el servicio de WCF** casilla de verificación para que se puede usar un itinerario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="d60a3-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be used.</span></span>  
  
4. <span data-ttu-id="d60a3-108">Seleccione el **dos servicios de manera** opción</span><span class="sxs-lookup"><span data-stu-id="d60a3-108">Select the **Two Way Service** option</span></span>  
  
5. <span data-ttu-id="d60a3-109">Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta de \Source\Samples\SqlAdapter \Itineraries.</span><span class="sxs-lookup"><span data-stu-id="d60a3-109">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the folder \Source\Samples\SqlAdapter \Itineraries.</span></span>  
  
6. <span data-ttu-id="d60a3-110">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo OrderDoc.xml en la carpeta de \Source\Samples\SqlAdapter \Test.</span><span class="sxs-lookup"><span data-stu-id="d60a3-110">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message in the folder \Source\Samples\SqlAdapter \Test.</span></span>  
  
7. <span data-ttu-id="d60a3-111">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="d60a3-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
8. <span data-ttu-id="d60a3-112">Asegúrese de que se inserta una fila en la tabla Product de la base de datos GlobalBankESB.</span><span class="sxs-lookup"><span data-stu-id="d60a3-112">Make sure one row is inserted in the Product table of the GlobalBankESB database.</span></span>  
  
   <span data-ttu-id="d60a3-113">Para obtener información acerca de cómo funciona el ejemplo de adaptador de SQL, vea [SQL adaptador de ejemplo de funcionamiento](../esb-toolkit/how-the-sql-adapter-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="d60a3-113">For information about how the SQL Adapter sample works, see [How the SQL Adapter Sample Works](../esb-toolkit/how-the-sql-adapter-sample-works.md).</span></span>