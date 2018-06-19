---
title: 'Paso 1: Hacer referencia a la DLL1 esquema | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47e4b773-e484-4931-9ab2-b8dd0080ea1c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c2d5051c7dfd3c0f971b34922ca4e5747117c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279444"
---
# <a name="step-1-reference-the-schema-dll"></a><span data-ttu-id="8e320-102">Paso 1: Hacer referencia al esquema DLL</span><span class="sxs-lookup"><span data-stu-id="8e320-102">Step 1: Reference the Schema DLL</span></span>
<span data-ttu-id="8e320-103">En BizTalk, los mensajes son inmutables.</span><span class="sxs-lookup"><span data-stu-id="8e320-103">In BizTalk, messages are immutable.</span></span> <span data-ttu-id="8e320-104">Por tanto, para cambiar un valor de propiedad, debe crear y modificar un nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="8e320-104">Therefore, to change a property value you must create and modify a new message.</span></span> <span data-ttu-id="8e320-105">Puede crear y modificar el nuevo mensaje mediante la inserción de una forma de asignación del mensaje entre las formas de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="8e320-105">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span>  
  
 <span data-ttu-id="8e320-106">No obstante, debe hacer referencia, en primer lugar, al esquema DLL para obtener acceso a las propiedades de contexto de J.D.</span><span class="sxs-lookup"><span data-stu-id="8e320-106">First, however, you must reference the schema DLL to gain access to the J.D.</span></span> <span data-ttu-id="8e320-107">Propiedades de contexto de Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="8e320-107">Edwards EnterpriseOne context properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="8e320-108">Para hacer referencia al esquema DLL</span><span class="sxs-lookup"><span data-stu-id="8e320-108">To reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="8e320-109">Cree una carpeta de trabajo, por ejemplo, c:\class\JDE\BeginDoc, para su proyecto, y una carpeta en la que pondrá el XML de prueba, por ejemplo, c:\class\JDE\input.</span><span class="sxs-lookup"><span data-stu-id="8e320-109">Create a working folder, for example, c:\class\JDE\BeginDoc, for your project and a folder in which you will put the test XML, for example, c:\class\JDE\input.</span></span>  
  
2.  <span data-ttu-id="8e320-110">Crear un puerto de envío de petición-respuesta estático para enviar la solicitud a J.D.</span><span class="sxs-lookup"><span data-stu-id="8e320-110">Create a Static Solicit-Response Send Port to send the request to J.D.</span></span> <span data-ttu-id="8e320-111">Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="8e320-111">Edwards EnterpriseOne.</span></span>  
  
     <span data-ttu-id="8e320-112">![Propiedades de transporte de JDOneWorld](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")</span><span class="sxs-lookup"><span data-stu-id="8e320-112">![JDOneWorld Transport Properties](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")</span></span>  
  
3.  <span data-ttu-id="8e320-113">En el editor de soluciones, haga clic con el botón secundario en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="8e320-113">In the Solution Editor, right-click your project.</span></span>  
  
    1.  <span data-ttu-id="8e320-114">Seleccione **agregar**, seleccione **agregar elementos generados**y, a continuación, haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="8e320-114">Select **Add**, select **Add Generated Items**, and then click **Add Adapter**.</span></span>  
  
    2.  <span data-ttu-id="8e320-115">Seleccione el adaptador de Microsoft BizTalk para J.D.</span><span class="sxs-lookup"><span data-stu-id="8e320-115">Select the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="8e320-116">Edwards EnterpriseOne y el puerto que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="8e320-116">Edwards EnterpriseOne and the port you just created.</span></span>  
  
    3.  <span data-ttu-id="8e320-117">En el **Asistente para agregar adaptador**, seleccione **CSALES\B4200310**.</span><span class="sxs-lookup"><span data-stu-id="8e320-117">In the **Add Adapter Wizard**, select **CSALES\B4200310**.</span></span>  
  
    4.  <span data-ttu-id="8e320-118">Haga clic en **finalizar** para generar el esquema que contiene el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8e320-118">Click **Finish** to generate the schema containing the format for the Message.</span></span>  
  
     <span data-ttu-id="8e320-119">![Asistente para agregar adaptador](../core/media/add-adapter-wizard.gif "add_adapter_wizard")</span><span class="sxs-lookup"><span data-stu-id="8e320-119">![Add Adapter Wizard](../core/media/add-adapter-wizard.gif "add_adapter_wizard")</span></span>  
  
4.  <span data-ttu-id="8e320-120">En Visual Studio, abra el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="8e320-120">In Visual Studio, open the Solution Explorer.</span></span>  
  
5.  <span data-ttu-id="8e320-121">Haga clic en **referencias**y, a continuación, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="8e320-121">Right-click **References**, and then select **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="8e320-122">En el **Agregar referencia** pantalla, haga clic en el **examinar** botón.</span><span class="sxs-lookup"><span data-stu-id="8e320-122">On the **Add Reference** screen, click the **Browse** button.</span></span>  
  
7.  <span data-ttu-id="8e320-123">En el **Seleccionar componente** pantalla, vaya a %SystemDrive%\Program programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span><span class="sxs-lookup"><span data-stu-id="8e320-123">On the **Select Component** screen, navigate to %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
8.  <span data-ttu-id="8e320-124">Seleccione **Microsoft.Adapters.JDEProperties.dll**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="8e320-124">Select **Microsoft.Adapters.JDEProperties.dll**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="8e320-125">En el **Agregar referencia** pantalla, el archivo DLL aparece en la **componentes seleccionados** sección.</span><span class="sxs-lookup"><span data-stu-id="8e320-125">On the **Add Reference** screen, the DLL appears in the **Selected Components** section.</span></span>  
  
     <span data-ttu-id="8e320-126">![Pantalla de selección de propiedades](../core/media/properties-selection.gif "properties_selection")</span><span class="sxs-lookup"><span data-stu-id="8e320-126">![Properties Selection screen](../core/media/properties-selection.gif "properties_selection")</span></span>  
  
10. <span data-ttu-id="8e320-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8e320-127">Click **OK**.</span></span>  
  
11. <span data-ttu-id="8e320-128">Haga doble clic en la orquestación para obtener acceso al Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="8e320-128">Double-click your orchestration to access the Orchestration Designer.</span></span>  
  
     <span data-ttu-id="8e320-129">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="8e320-129">\- OR -</span></span>  
  
     <span data-ttu-id="8e320-130">Seleccione **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="8e320-130">Select **View**, select **Other Windows**, and then click **Orchestration View**.</span></span>  
  
     <span data-ttu-id="8e320-131">Aparecerá la Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="8e320-131">The Orchestration View appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e320-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e320-132">See Also</span></span>  
 <span data-ttu-id="8e320-133">[Paso 2: Crear la orquestación](../core/step-2-create-the-orchestration2.md) </span><span class="sxs-lookup"><span data-stu-id="8e320-133">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration2.md) </span></span>  
 <span data-ttu-id="8e320-134">[Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="8e320-134">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 <span data-ttu-id="8e320-135">[Tarea 5: Configurar la forma transformación](../core/task-5-configure-the-transform-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="8e320-135">[Task 5: Configure the Transform Shape](../core/task-5-configure-the-transform-shape2.md) </span></span>  
 <span data-ttu-id="8e320-136">[Paso 3: Completar y ejecutar el proyecto](../core/step-3-complete-and-run-the-project1.md) </span><span class="sxs-lookup"><span data-stu-id="8e320-136">[Step 3: Complete and Run the Project](../core/step-3-complete-and-run-the-project1.md) </span></span>  
 [<span data-ttu-id="8e320-137">Paso 4: Crear un XML de ejemplo de BeginDoc</span><span class="sxs-lookup"><span data-stu-id="8e320-137">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc2.md)