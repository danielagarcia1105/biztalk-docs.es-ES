---
title: Ejecuta las pruebas de componente de Namespace | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13768608-ade6-44c0-897f-d417c3408302
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae865e91fd6ff796cb870c71840bde8a95831e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-namespace-component-tests"></a><span data-ttu-id="36f22-102">Ejecuta las pruebas de componente de Namespace</span><span class="sxs-lookup"><span data-stu-id="36f22-102">Running the Namespace Component Tests</span></span>
<span data-ttu-id="36f22-103">El siguiente procedimiento muestra cómo ejecutar los cuatro de los escenarios de prueba para el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] del ejemplo de componente de Namespace.</span><span class="sxs-lookup"><span data-stu-id="36f22-103">The following procedure shows how you can run all four of the test scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Namespace Component sample.</span></span>  
  
 <span data-ttu-id="36f22-104">**Para ejecutar el componente de Namespace escenarios de prueba de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="36f22-104">**To run the Namespace Component sample test scenarios**</span></span>  
  
1.  <span data-ttu-id="36f22-105">Antes de ejecutar este ejemplo por primera vez, asegúrese de que la recepción dirección URL de puerto de ubicación y envío apuntar a las subcarpetas correspondientes en los archivos de distribución de origen.</span><span class="sxs-lookup"><span data-stu-id="36f22-105">Before you run this sample for the first time, make sure that the receive location and send port URL point to the appropriate subfolders in the source distribution files.</span></span> <span data-ttu-id="36f22-106">Especifique el \Source\Samples\Namespace\Test\Filedrop\In subcarpeta de la ubicación de recepción y el \Source\Samples\Namespace\Test\Filedrop\Out subcarpeta para la dirección URL de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="36f22-106">Specify the subfolder \Source\Samples\Namespace\Test\Filedrop\In for the receive location and the subfolder \Source\Samples\Namespace\Test\Filedrop\Out for the send port URL.</span></span>  
  
2.  <span data-ttu-id="36f22-107">Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="36f22-107">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
3.  <span data-ttu-id="36f22-108">Realice una copia del archivo denominado TEST_Add_to_PassThrough.0000.ns.xml (que se encuentra en la subcarpeta \Source\Samples\Namespace\Test\Data\ de la carpeta de instalación de ESB) y cambiar el nombre de la copia mediante la eliminación del prefijo "TEST_".</span><span class="sxs-lookup"><span data-stu-id="36f22-108">Make a copy of the file named TEST_Add_to_PassThrough.0000.ns.xml (located in the \Source\Samples\Namespace\Test\Data\ subfolder of your ESB installation folder), and rename the copy by removing the "TEST_" prefix.</span></span>  
  
4.  <span data-ttu-id="36f22-109">Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.</span><span class="sxs-lookup"><span data-stu-id="36f22-109">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
5.  <span data-ttu-id="36f22-110">ESB recoge el mensaje, agrega un espacio de nombres y coloca el mensaje actualizado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\Out.</span><span class="sxs-lookup"><span data-stu-id="36f22-110">The ESB picks up the message, adds a namespace to it, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="36f22-111">Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.</span><span class="sxs-lookup"><span data-stu-id="36f22-111">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
6.  <span data-ttu-id="36f22-112">Ahora ejecute la segunda prueba.</span><span class="sxs-lookup"><span data-stu-id="36f22-112">Now run the second test.</span></span> <span data-ttu-id="36f22-113">Realizar una copia del archivo denominado TEST_Add_to_Remove.0000.ns.xml y cambie su nombre mediante la eliminación del prefijo "TEST_".</span><span class="sxs-lookup"><span data-stu-id="36f22-113">Make a copy of the file named TEST_Add_to_Remove.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
7.  <span data-ttu-id="36f22-114">Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.</span><span class="sxs-lookup"><span data-stu-id="36f22-114">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
8.  <span data-ttu-id="36f22-115">ESB recoge el mensaje, agrega un espacio de nombres, quita el espacio de nombres nuevo y coloca el mensaje actualizado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\Out.</span><span class="sxs-lookup"><span data-stu-id="36f22-115">The ESB picks up the message, adds a namespace to it, removes the new namespace, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="36f22-116">Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.</span><span class="sxs-lookup"><span data-stu-id="36f22-116">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
9. <span data-ttu-id="36f22-117">Ahora ejecute la prueba terceros.</span><span class="sxs-lookup"><span data-stu-id="36f22-117">Now run the third test.</span></span> <span data-ttu-id="36f22-118">Realizar una copia del archivo denominado TEST_PassThrough_to_Remove.0000.ns.xml y cambie su nombre mediante la eliminación del prefijo "TEST_".</span><span class="sxs-lookup"><span data-stu-id="36f22-118">Make a copy of the file named TEST_PassThrough_to_Remove.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
10. <span data-ttu-id="36f22-119">Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.</span><span class="sxs-lookup"><span data-stu-id="36f22-119">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
11. <span data-ttu-id="36f22-120">ESB recoge el mensaje, quita el espacio de nombres existente y coloca el mensaje actualizado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\Out.</span><span class="sxs-lookup"><span data-stu-id="36f22-120">The ESB picks up the message, removes the existing namespace, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="36f22-121">Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.</span><span class="sxs-lookup"><span data-stu-id="36f22-121">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
12. <span data-ttu-id="36f22-122">Por último, ejecute la cuarta de pruebas.</span><span class="sxs-lookup"><span data-stu-id="36f22-122">Finally, run the fourth test.</span></span> <span data-ttu-id="36f22-123">Realizar una copia del archivo denominado TEST_AddViaExtraction_to_PassThrough.0000.ns.xml y cambie su nombre mediante la eliminación del prefijo "TEST_".</span><span class="sxs-lookup"><span data-stu-id="36f22-123">Make a copy of the file named TEST_AddViaExtraction_to_PassThrough.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
13. <span data-ttu-id="36f22-124">Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.</span><span class="sxs-lookup"><span data-stu-id="36f22-124">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
14. <span data-ttu-id="36f22-125">ESB recoge el mensaje, se extrae el elemento especificado en el **ExtractionNodeXPath** propiedad, crea un mensaje de este elemento con los valores de espacio de nombres especificado y coloca el mensaje actualizado en el \Source\Samples\ Subcarpeta Namespace\Test\Filedrop\Out.</span><span class="sxs-lookup"><span data-stu-id="36f22-125">The ESB picks up the message, extracts the element specified in the **ExtractionNodeXPath** property, creates a message from this element with the specified namespace values, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="36f22-126">Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.</span><span class="sxs-lookup"><span data-stu-id="36f22-126">Open the input and output files in a text editor to see the effect of this test.</span></span>