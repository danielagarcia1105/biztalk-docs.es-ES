---
title: 'Paso 1: Hacer referencia a la DLL2 esquema | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1db92227-6164-42b9-b60c-12dd2cae46e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b009e2c79c0ea68030561c51e3a90ceef24eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277532"
---
# <a name="step-1-reference-the-schema-dll"></a><span data-ttu-id="c537e-102">Paso 1: Hacer referencia al esquema DLL</span><span class="sxs-lookup"><span data-stu-id="c537e-102">Step 1: Reference the Schema DLL</span></span>
<span data-ttu-id="c537e-103">En BizTalk, los mensajes son inmutables.</span><span class="sxs-lookup"><span data-stu-id="c537e-103">In BizTalk, messages are immutable.</span></span> <span data-ttu-id="c537e-104">Por tanto, para cambiar un valor de propiedad, debe crear y modificar un nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="c537e-104">Therefore, to change a property value you must create and modify a new message.</span></span> <span data-ttu-id="c537e-105">Puede crear y modificar el nuevo mensaje mediante la inserción de una forma de asignación del mensaje entre las formas de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="c537e-105">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span>  
  
 <span data-ttu-id="c537e-106">No obstante, debe hacer referencia, en primer lugar, al esquema DLL para obtener acceso a las propiedades de contexto de J.D.</span><span class="sxs-lookup"><span data-stu-id="c537e-106">First, however, you must reference the schema DLL to gain access to the J.D.</span></span> <span data-ttu-id="c537e-107">Propiedades de contexto de Edwards.</span><span class="sxs-lookup"><span data-stu-id="c537e-107">Edwards context properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="c537e-108">Para hacer referencia al esquema DLL</span><span class="sxs-lookup"><span data-stu-id="c537e-108">To reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="c537e-109">Cree una carpeta de trabajo, por ejemplo, c:\class\JDE\BeginDoc, para su proyecto, y una carpeta en la que pondrá el XML de prueba, por ejemplo, c:\class\JDE\input.</span><span class="sxs-lookup"><span data-stu-id="c537e-109">Create a working folder, for example, c:\class\JDE\BeginDoc, for your project and a folder in which you will put the test XML, for example, c:\class\JDE\input.</span></span>  
  
2.  <span data-ttu-id="c537e-110">Crear un puerto de envío de petición-respuesta estático para enviar la solicitud a J.D.</span><span class="sxs-lookup"><span data-stu-id="c537e-110">Create a Static Solicit-Response Send Port to send the request to J.D.</span></span> <span data-ttu-id="c537e-111">Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="c537e-111">Edwards OneWorld.</span></span>  
  
     ![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")  
  
3.  <span data-ttu-id="c537e-112">En el editor de soluciones, haga clic con el botón secundario en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="c537e-112">In the Solution Editor, right-click your project.</span></span>  
  
    1.  <span data-ttu-id="c537e-113">Seleccione **agregar**, seleccione **agregar elementos generados**y, a continuación, haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="c537e-113">Select **Add**, select **Add Generated Items**, and then click **Add Adapter**.</span></span>  
  
    2.  <span data-ttu-id="c537e-114">Seleccione el adaptador de Microsoft BizTalk para J.D.</span><span class="sxs-lookup"><span data-stu-id="c537e-114">Select the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="c537e-115">Edwards OneWorld y el puerto que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="c537e-115">Edwards OneWorld and the port you just created.</span></span>  
  
    3.  <span data-ttu-id="c537e-116">En el **Asistente para agregar adaptador**, seleccione **CSALES\B4200310**.</span><span class="sxs-lookup"><span data-stu-id="c537e-116">In the **Add Adapter Wizard**, select **CSALES\B4200310**.</span></span>  
  
    4.  <span data-ttu-id="c537e-117">Haga clic en **finalizar** para generar el esquema que contiene el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c537e-117">Click **Finish** to generate the schema containing the format for the Message.</span></span>  
  
     ![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")  
  
4.  <span data-ttu-id="c537e-118">En Visual Studio, abra el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="c537e-118">In Visual Studio, open the Solution Explorer.</span></span>  
  
5.  <span data-ttu-id="c537e-119">Haga clic en **referencias**y, a continuación, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="c537e-119">Right-click **References**, and then select **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="c537e-120">En el **Agregar referencia** pantalla, haga clic en el **examinar** botón.</span><span class="sxs-lookup"><span data-stu-id="c537e-120">On the **Add Reference** screen, click the **Browse** button.</span></span>  
  
     ![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")  
  
7.  <span data-ttu-id="c537e-121">En el **Seleccionar componente** pantalla, vaya a %SystemDrive%\Program programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span><span class="sxs-lookup"><span data-stu-id="c537e-121">On the **Select Component** screen, navigate to %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
8.  <span data-ttu-id="c537e-122">Seleccione **Microsoft.Adapters.JDEProperties.dll**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="c537e-122">Select **Microsoft.Adapters.JDEProperties.dll**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="c537e-123">En el **Agregar referencia** pantalla, el archivo DLL aparece en la **componentes seleccionados** sección.</span><span class="sxs-lookup"><span data-stu-id="c537e-123">On the **Add Reference** screen, the DLL appears in the **Selected Components** section.</span></span>  
  
     ![](../core/media/jde-properties-selection.gif "JDE_properties_selection")  
  
10. <span data-ttu-id="c537e-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c537e-124">Click **OK**.</span></span>  
  
11. <span data-ttu-id="c537e-125">Haga doble clic en la orquestación para obtener acceso al Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="c537e-125">Double-click your orchestration to access the Orchestration Designer.</span></span>  
  
     <span data-ttu-id="c537e-126">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="c537e-126">\- OR -</span></span>  
  
     <span data-ttu-id="c537e-127">Seleccione **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="c537e-127">Select **View**, select **Other Windows**, and then click **Orchestration View**.</span></span>  
  
     <span data-ttu-id="c537e-128">Aparecerá la Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="c537e-128">The Orchestration View appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c537e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="c537e-129">See Also</span></span>  
 <span data-ttu-id="c537e-130">[Paso 2: Crear la orquestación](../core/step-2-create-the-orchestration1.md) </span><span class="sxs-lookup"><span data-stu-id="c537e-130">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration1.md) </span></span>  
 <span data-ttu-id="c537e-131">[Paso 3: Completar y ejecutar el proyecto](../core/step-3-complete-and-run-the-project2.md) </span><span class="sxs-lookup"><span data-stu-id="c537e-131">[Step 3: Complete and Run the Project](../core/step-3-complete-and-run-the-project2.md) </span></span>  
 [<span data-ttu-id="c537e-132">Paso 4: Crear un XML de ejemplo de BeginDoc</span><span class="sxs-lookup"><span data-stu-id="c537e-132">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)