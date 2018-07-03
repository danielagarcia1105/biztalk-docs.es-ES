---
title: Depurar orquestaciones mediante código personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, debugging
- building, debugging
ms.assetid: 94e569fa-8dea-4027-abb5-37b4a8015621
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e32358f48099b9d184a9ff1ff62a0a85af595b89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995341"
---
# <a name="debugging-orchestrations-by-using-custom-code"></a><span data-ttu-id="0542c-102">Depurar orquestaciones mediante Código personalizado</span><span class="sxs-lookup"><span data-stu-id="0542c-102">Debugging Orchestrations by using Custom Code</span></span>
<span data-ttu-id="0542c-103">Si la orquestación que se va a emplear en un entorno de prueba o está creando un prototipo y desea modificar los valores de los campos de mensajes y variables de orquestación, puede escribir la salida a la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] consola mediante el siguiente código en un  **Expresión** forma:</span><span class="sxs-lookup"><span data-stu-id="0542c-103">If your orchestration is going to be exercised in a test environment or you are creating a prototype and want to modify the values of message fields and orchestration variables, you can write the output to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] console by using the following code in an **Expression** shape:</span></span>  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 <span data-ttu-id="0542c-104">Tendrá que colocar esto **expresión** forma inmediatamente después de la forma en que realiza la operación para que se pueda pasar el resultado para la depuración.</span><span class="sxs-lookup"><span data-stu-id="0542c-104">You need to place this **Expression** shape immediately after the shape that performs the operation so that you can output the result for debugging.</span></span>  
  
 <span data-ttu-id="0542c-105">Asimismo, puede escribir un depurador personalizado sencillo al crear un archivo DLL de depuración con una clase que incluya un método que tome como entrada un mensaje cuyo formato se haya definido en la orquestación y al que se haya hecho referencia en el archivo DLL de depuración.</span><span class="sxs-lookup"><span data-stu-id="0542c-105">Alternatively, you can write a simple custom debugger by creating a debugging DLL with a class that includes a method which takes as input a message with a format defined in your orchestration and referenced in the debug DLL.</span></span> <span data-ttu-id="0542c-106">Para obtener más información acerca de cómo pasar un mensaje como un parámetro, vea [cómo usar expresiones para crear objetos y llamar a métodos del objeto](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0542c-106">For more information about passing a message as a parameter, see [How to Use Expressions to Create Objects and Call Object Methods](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md).</span></span>  
  
 <span data-ttu-id="0542c-107">Este método puede abrir un cuadro de diálogo de depuración que incluye un cuadro combinado u otro control que le permite al usuario modificar los valores, volver a reunir los mensajes editados y devolverlos como el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0542c-107">This method can bring up a debug dialog that includes a combo box or other control to allow user modification of values, puts the edited message back together, and passes it back out as the return value.</span></span>  
  
 <span data-ttu-id="0542c-108">Configurar una variable booleana para indicar si la orquestación está en modo de depuración y, después, siempre que tiene un punto en la orquestación a la que le gustaría poder modificar los valores, puede agregar un **decidir** forma con uno en vivo rama que se ejecuta solo cuando la variable de modo de depuración está establecida en True, o cuando se produzca una condición determinada que desea examinar.</span><span class="sxs-lookup"><span data-stu-id="0542c-108">Set up a Boolean variable to indicate whether or not your orchestration is in debug mode, then wherever you have a point in your orchestration at which you would like to be able to modify values, you can add a **Decide** shape with one live branch that runs only when your debug mode variable is set to True, or when a particular condition arises that you want to examine.</span></span> <span data-ttu-id="0542c-109">Se llama al método desde un **expresión** forma en la rama activa de la **decidir**.</span><span class="sxs-lookup"><span data-stu-id="0542c-109">You call your method from an **Expression** shape in the live branch of the **Decide**.</span></span> <span data-ttu-id="0542c-110">Cuando ya no necesite depurar, se establece la variable de modo de depuración en False o se quita el **decidir** forma o formas completamente y vuelva a compilar.</span><span class="sxs-lookup"><span data-stu-id="0542c-110">When you no longer need to debug, you set your debug mode variable to False, or remove the **Decide** shape(s) altogether and recompile.</span></span>  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a><span data-ttu-id="0542c-111">Para depurar un componente .NET al que llama una orquestación</span><span class="sxs-lookup"><span data-stu-id="0542c-111">To Debug a .NET component called by an Orchestration</span></span>  
 <span data-ttu-id="0542c-112">Los pasos siguientes muestran cómo depurar un componente .NET al que llama una orquestación:</span><span class="sxs-lookup"><span data-stu-id="0542c-112">The following steps demonstrate how to debug a .NET component called by an Orchestration:</span></span>  
  
1. <span data-ttu-id="0542c-113">Abra el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para el componente.</span><span class="sxs-lookup"><span data-stu-id="0542c-113">Open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for your component.</span></span>  
  
2. <span data-ttu-id="0542c-114">Configure un punto de interrupción del componente en el método que llama la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0542c-114">Set a breakpoint in your component on the method that is called by the orchestration.</span></span>  
  
3. <span data-ttu-id="0542c-115">Haga clic en el **depurar** menú y seleccione **asociar al proceso...**</span><span class="sxs-lookup"><span data-stu-id="0542c-115">Click the **Debug** menu and select **Attach to Process…**</span></span> <span data-ttu-id="0542c-116">para mostrar el **asociar al proceso** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0542c-116">to display the **Attach to Process** dialog.</span></span>  
  
4. <span data-ttu-id="0542c-117">Haga clic en el **seleccione...**</span><span class="sxs-lookup"><span data-stu-id="0542c-117">Click the **Select…**</span></span> <span data-ttu-id="0542c-118">situado junto a la **adjuntar a:** cuadro de texto para mostrar el **Seleccionar tipo de código** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0542c-118">button next to the **Attach to:** text box to display the **Select Code Type** dialog.</span></span>  
  
5. <span data-ttu-id="0542c-119">Haga clic para seleccionar la opción de **depurar estos tipos de código:** y seleccione **administrada** y, a continuación, haga clic en el **Aceptar** botón.</span><span class="sxs-lookup"><span data-stu-id="0542c-119">Click to select the option to **Debug these code types:** and select **Managed** and then click the **OK** button.</span></span>  
  
6. <span data-ttu-id="0542c-120">Haga clic para seleccionar el **BTSNTSvc.exe** procesos de **procesos disponibles** y, a continuación, haga clic en el **adjuntar** botón.</span><span class="sxs-lookup"><span data-stu-id="0542c-120">Click to select the **BTSNTSvc.exe** process from **Available Processes** and then click the **Attach** button.</span></span>  
  
7. <span data-ttu-id="0542c-121">Envíe un mensaje a la orquestación mediante un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0542c-121">Send a message to your orchestration through a receive port.</span></span>  
  
8. <span data-ttu-id="0542c-122">Se debería detener el componente .NET en el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="0542c-122">The .NET component should be stopped in the breakpoint.</span></span>  
  
9. <span data-ttu-id="0542c-123">Puede realizar la depuración como de costumbre con [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0542c-123">You can perform debugging as usual with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0542c-124">Para obtener mejores resultados, se debería registrar el componente .NET en la Caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="0542c-124">For best results, the .NET component should be registered in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0542c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0542c-125">See Also</span></span>  
 <span data-ttu-id="0542c-126">[Interfaz de usuario del depurador de orquestaciones](../core/orchestration-debugger-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="0542c-126">[Orchestration Debugger User Interface](../core/orchestration-debugger-user-interface.md) </span></span>  
 [<span data-ttu-id="0542c-127">Depuración de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="0542c-127">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)