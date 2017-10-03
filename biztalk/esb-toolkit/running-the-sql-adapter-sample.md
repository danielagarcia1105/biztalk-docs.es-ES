---
title: Ejecutar el ejemplo de adaptador SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13566d08-7a59-4065-b0d7-19ae2765555e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf04c06a1ef96974912ce3affe278d5a98936325
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-sql-adapter-sample"></a><span data-ttu-id="d91a8-102">Ejecutar el ejemplo de adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="d91a8-102">Running the SQL Adapter Sample</span></span>
<span data-ttu-id="d91a8-103">El ejemplo de adaptador de SQL utiliza una aplicación de cliente de prueba de Windows Forms suministrada con el ejemplo de itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="d91a8-103">The SQL Adapter sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="d91a8-104">**Para ejecutar el ejemplo de adaptador de SQL**</span><span class="sxs-lookup"><span data-stu-id="d91a8-104">**To run the SQL Adapter sample**</span></span>  
  
1.  <span data-ttu-id="d91a8-105">Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="d91a8-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="d91a8-106">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="d91a8-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="d91a8-107">Desactive el **usar el servicio de WCF** casilla de verificación para que se puede utilizar un itinerario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="d91a8-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be used.</span></span>  
  
4.  <span data-ttu-id="d91a8-108">Seleccione el **dos servicios de manera** opción</span><span class="sxs-lookup"><span data-stu-id="d91a8-108">Select the **Two Way Service** option</span></span>  
  
5.  <span data-ttu-id="d91a8-109">Haga clic en el **carga itinerario** botón y, a continuación, seleccione uno de los itinerarios de ejemplo ubicados en la carpeta \Source\Samples\SqlAdapter \Itineraries.</span><span class="sxs-lookup"><span data-stu-id="d91a8-109">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the folder \Source\Samples\SqlAdapter \Itineraries.</span></span>  
  
6.  <span data-ttu-id="d91a8-110">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo OrderDoc.xml en la carpeta \Source\Samples\SqlAdapter \Test.</span><span class="sxs-lookup"><span data-stu-id="d91a8-110">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message in the folder \Source\Samples\SqlAdapter \Test.</span></span>  
  
7.  <span data-ttu-id="d91a8-111">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="d91a8-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
8.  <span data-ttu-id="d91a8-112">Asegúrese de que se inserta una fila en la tabla Product de la base de datos de GlobalBankESB.</span><span class="sxs-lookup"><span data-stu-id="d91a8-112">Make sure one row is inserted in the Product table of the GlobalBankESB database.</span></span>  
  
 <span data-ttu-id="d91a8-113">Para obtener información sobre cómo funciona el ejemplo del adaptador de SQL, consulte [SQL adaptador de ejemplo de funcionamiento del](../esb-toolkit/how-the-sql-adapter-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="d91a8-113">For information about how the SQL Adapter sample works, see [How the SQL Adapter Sample Works](../esb-toolkit/how-the-sql-adapter-sample-works.md).</span></span>