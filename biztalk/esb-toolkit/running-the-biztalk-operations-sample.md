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
# <a name="running-the-biztalk-operations-sample"></a><span data-ttu-id="7a858-102">Ejecutar el ejemplo de operaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7a858-102">Running the BizTalk Operations Sample</span></span>
<span data-ttu-id="7a858-103">El ejemplo de operaciones de Microsoft BizTalk utiliza una aplicación de cliente de prueba de Windows Forms para ejecutar métodos del servicio Web de las operaciones de BizTalk y mostrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="7a858-103">The Microsoft BizTalk Operations sample uses a Windows Forms test client application to execute methods of the BizTalk Operations Web service and display the results.</span></span> <span data-ttu-id="7a858-104">Puede abrir el proyecto de cliente de prueba para ejecutarlo y examinar el código para ver cómo puede usar el servicio Web de las operaciones de BizTalk en su propia arquitectura orientada a servicios (SOA) y aplicaciones de ESB.</span><span class="sxs-lookup"><span data-stu-id="7a858-104">You can open the test client project to run it and to examine the code to see how you can use the BizTalk Operations Web service in your own service-oriented architecture (SOA) and ESB applications.</span></span>  
  
 <span data-ttu-id="7a858-105">En el Explorador de Windows, abra la carpeta denominada \Samples\BizTalkOperations\bin\Debug y, a continuación, ejecute la aplicación Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe.</span><span class="sxs-lookup"><span data-stu-id="7a858-105">In Windows Explorer, open the folder named \Samples\BizTalkOperations\bin\Debug, and then execute the application Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe.</span></span>  
  
 <span data-ttu-id="7a858-106">La figura 1 muestra la aplicación de cliente de prueba para el servicio Web de las operaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7a858-106">Figure 1 shows the test client application for the BizTalk Operations Web service.</span></span> <span data-ttu-id="7a858-107">Puede ejecutar todas las funciones del servicio Web de las operaciones de BizTalk con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a858-107">You can execute all the functions of the BizTalk Operations Web service using this application.</span></span> <span data-ttu-id="7a858-108">La aplicación muestra los resultados en un formato de vista de árbol y muestra el mensaje devuelto por el servicio.</span><span class="sxs-lookup"><span data-stu-id="7a858-108">The application displays the results in a tree-view format and shows the message returned by the service.</span></span>  
  
 <span data-ttu-id="7a858-109">![Prueba de servicio de Web](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")</span><span class="sxs-lookup"><span data-stu-id="7a858-109">![Web Service Test](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")</span></span>  
  
 <span data-ttu-id="7a858-110">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="7a858-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="7a858-111">**El cliente de prueba del servicio Web de BizTalk operaciones**</span><span class="sxs-lookup"><span data-stu-id="7a858-111">**The BizTalk Operations Web Service Test Client**</span></span>  
  
 <span data-ttu-id="7a858-112">Para ejecutar un método del servicio Web de las operaciones de BizTalk que no requiere ningún parámetro, simplemente haga clic en el botón correspondiente en el lado izquierdo de la ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a858-112">To execute a method of the BizTalk Operations Web service that does not require any parameters, simply click the appropriate button in the left side of the application window.</span></span> <span data-ttu-id="7a858-113">Para los métodos que requieren parámetros de entrada, seleccione el método en la lista desplegable en la parte superior de la ventana, escriba los valores de parámetro necesita y, a continuación, haga clic en el **invocar servicio** botón.</span><span class="sxs-lookup"><span data-stu-id="7a858-113">For methods that do require input parameters, select the method in the drop-down list at the top of the window, enter the parameter values you require, and then click the **Invoke Service** button.</span></span>  
  
## <a name="how-the-sample-works"></a><span data-ttu-id="7a858-114">Cómo funciona el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a858-114">How the Sample Works</span></span>  
 <span data-ttu-id="7a858-115">La aplicación de ejemplo crea una instancia del servicio Web de las operaciones de BizTalk ESB y llama al método adecuado según la configuración que seleccione en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a858-115">The sample application instantiates the ESB BizTalk Operations Web service and calls the appropriate method depending on the settings you select in the application.</span></span> <span data-ttu-id="7a858-116">Pasa los valores que escriba en los controles de la aplicación como parámetros al método de servicio seleccionada y recopila la salida desde el método de servicio para mostrar en la ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a858-116">It passes the value(s) you enter in the application controls as parameters to the selected service method, and it collects the output from the service method to display in the application window.</span></span>