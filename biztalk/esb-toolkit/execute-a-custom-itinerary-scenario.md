---
title: Ejecutar un escenario de itinerarios personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc7b746f636b6f90462d296f12827fb0492dd23
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009557"
---
# <a name="execute-a-custom-itinerary-scenario"></a><span data-ttu-id="edb8c-102">Ejecutar un escenario de itinerarios personalizado</span><span class="sxs-lookup"><span data-stu-id="edb8c-102">Execute a Custom Itinerary Scenario</span></span>
<span data-ttu-id="edb8c-103">Puede usar el cliente de prueba de itinerario aplicación ejecutar escenarios de itinerarios personalizados.</span><span class="sxs-lookup"><span data-stu-id="edb8c-103">You can use the Itinerary Test Client application execute custom itinerary scenarios.</span></span>  

### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a><span data-ttu-id="edb8c-104">Para ejecutar un escenario de itinerarios personalizado mediante la aplicación cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="edb8c-104">To execute a custom itinerary scenario using the Itinerary Test Client application</span></span>  

1. <span data-ttu-id="edb8c-105">En el Explorador de Windows, abra la carpeta \Source\Samples\Itinerary\Source\ESB. Itinerary.Test\bin\Debug donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos e iniciar la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="edb8c-105">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples and start the application named Esb.Itinerary.Test.exe.</span></span>  

2. <span data-ttu-id="edb8c-106">Seleccione un tipo de servicio en la **ServiceType** la lista desplegable, especifique un nombre para la solicitud y, a continuación, seleccione el **IsRequestResponse** casilla de verificación si se trata de una operación de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="edb8c-106">Select a service type in the **ServiceType** drop-down list, specify a name for the request, and then select the **IsRequestResponse** check box if this is a request/response operation.</span></span> <span data-ttu-id="edb8c-107">Puede especificar una operación bidireccional y optar por usar la versión WCF del servicio Web de itinerarios. Para ello, active las casillas de verificación en la **opciones del servicio Web** en la parte superior de la ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edb8c-107">You can specify a two-way operation and choose to use the WCF version of the Itinerary Web service; to do this, select the check boxes in the **Web Service Options** section at the top of the application window.</span></span>  

3. <span data-ttu-id="edb8c-108">Para especificar las resoluciones para usar con el servicio seleccionado en el **AddResolversfortheService** sección de la ventana, seleccione una resolución de tipo en la lista desplegable y, a continuación, haga clic en **AddResolver**.</span><span class="sxs-lookup"><span data-stu-id="edb8c-108">To specify the resolvers to use with the selected service in the **AddResolversfortheService** section of the window, select a resolver type from the drop-down list, and then click **AddResolver**.</span></span> <span data-ttu-id="edb8c-109">Puede agregar a más de una resolución si es necesario.</span><span class="sxs-lookup"><span data-stu-id="edb8c-109">You can add more than one resolver if required.</span></span> <span data-ttu-id="edb8c-110">Después de agregar todas las resoluciones necesarias, haga clic en el **AddService** para agregar esta invocación de servicio para el itinerario.</span><span class="sxs-lookup"><span data-stu-id="edb8c-110">After you add all the required resolvers, click the **AddService** button to add this service invocation to the itinerary.</span></span>  

4. <span data-ttu-id="edb8c-111">Si desea agregar más invocaciones de servicio para el itinerario, repita los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="edb8c-111">If you want to add more service invocations to the itinerary, repeat steps 2 and 3.</span></span> <span data-ttu-id="edb8c-112">También puede usar el **RemoveService** y **ClearServices** botones para modificar la lista de servicios en el itinerario.</span><span class="sxs-lookup"><span data-stu-id="edb8c-112">You can also use the **RemoveService** and **ClearServices** buttons to modify the list of services in the itinerary.</span></span>  

5. <span data-ttu-id="edb8c-113">Si desea repetir el itinerario actual en otro momento, guarde el itinerario completo actual en el disco, haga clic en el **SaveItinerary** botón.</span><span class="sxs-lookup"><span data-stu-id="edb8c-113">If you want to repeat the current itinerary at another time, save the complete current itinerary to disk by clicking the **SaveItinerary** button.</span></span> <span data-ttu-id="edb8c-114">Puede cargar de nuevo, haga clic en el **LoadItinerary** botón.</span><span class="sxs-lookup"><span data-stu-id="edb8c-114">You can load it again by clicking the **LoadItinerary** button.</span></span> <span data-ttu-id="edb8c-115">Esto significa que no es necesario especificar los servicios y las resoluciones en el itinerario cada vez que ejecute este escenario con diferentes mensajes o la configuración del servicio Web de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="edb8c-115">This means that you do not have to specify the services and resolvers in the itinerary every time you execute this scenario with different messages or Itinerary Web service settings.</span></span>  

6. <span data-ttu-id="edb8c-116">Cargar un mensaje adecuado.</span><span class="sxs-lookup"><span data-stu-id="edb8c-116">Load a suitable message.</span></span> <span data-ttu-id="edb8c-117">Para ello, escriba la ruta de acceso y el nombre del mensaje en el **LoadMessage** texto cuadro o haga clic en el botón de puntos suspensivos (...) y, a continuación, seleccione el archivo de mensaje necesarios.</span><span class="sxs-lookup"><span data-stu-id="edb8c-117">To do this, either type the path and name of the message in the **LoadMessage** text box or click the ellipsis button (...), and then select the required message file.</span></span>  

7. <span data-ttu-id="edb8c-118">Haga clic en el **SubmitRequest** botón para enviar el mensaje para el procesamiento con la configuración de itinerarios especificada.</span><span class="sxs-lookup"><span data-stu-id="edb8c-118">Click the **SubmitRequest** button to submit the message for processing with the itinerary settings you specified.</span></span> <span data-ttu-id="edb8c-119">Si el procesamiento devuelve un resultado, esta descripción aparecerá en la **resultado** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="edb8c-119">If the processing returns a result, this will appear in the **Result** text box.</span></span>
