---
title: "Cómo agregar Variables de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, variables
ms.assetid: c387cd56-5443-4de2-bbda-be34b95cbe71
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4416534bdd73e8ae6eeeca28165ebc62c11bfc92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-orchestration-variables"></a><span data-ttu-id="389e9-102">Cómo agregar variables de orquestación</span><span class="sxs-lookup"><span data-stu-id="389e9-102">How to Add Orchestration Variables</span></span>
<span data-ttu-id="389e9-103">La ventana Vista orquestación permite administrar las propiedades de una orquestación (también conocido como **servicio** propiedades), parámetros, puertos, mensajes y otras variables.</span><span class="sxs-lookup"><span data-stu-id="389e9-103">The Orchestration View window enables you to manage an orchestration's properties (also known as **Service** properties), parameters, ports, messages, and other variables.</span></span> <span data-ttu-id="389e9-104">Además de los puertos y mensajes, puede crear variables de tipo entero, variables booleanas, variables de cadena o variables de una clase .NET.</span><span class="sxs-lookup"><span data-stu-id="389e9-104">In addition to ports and messages, you can create integer variables, Boolean variables, string variables, or variables of a .NET class.</span></span>  
  
 <span data-ttu-id="389e9-105">Asimismo, puede usar la ventana Vista orquestación para administrar las variables que pertenecen a los ámbitos.</span><span class="sxs-lookup"><span data-stu-id="389e9-105">You can also use the Orchestration View window to manage the variables that belong to your scopes.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="389e9-106">Para agregar una variable</span><span class="sxs-lookup"><span data-stu-id="389e9-106">To add a variable</span></span>  
  
1.  <span data-ttu-id="389e9-107">En la ventana Vista orquestación, haga clic en el **Variables** carpeta y, a continuación, haga clic en **nueva Variable**.</span><span class="sxs-lookup"><span data-stu-id="389e9-107">In the Orchestration View window, right-click the **Variables** folder and then click **New Variable**.</span></span>  
  
     <span data-ttu-id="389e9-108">El **Variables** carpeta se expande, si se contrae, y se agrega una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="389e9-108">The **Variables** folder expands, if collapsed, and a new variable is added.</span></span>  
  
2.  <span data-ttu-id="389e9-109">Asígnele un nombre a la variable mediante la escritura de un nombre en la propiedad Identificador de la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="389e9-109">Name the variable by typing a name in the Identifier property in the Properties window.</span></span>  
  
3.  <span data-ttu-id="389e9-110">Asocie la variable con un tipo, por ejemplo, una clase .NET.</span><span class="sxs-lookup"><span data-stu-id="389e9-110">Associate the variable with a type, such as a .NET class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="389e9-111">El **tipos** lista desplegable contiene los siguientes tipos de variables predefinidos: **booleano**, **bytes**, **datetime**,  **decimal**, **doble**, **int16**, **int32**, **int64**, **sbyte** , **único**, **cadena**, **timespan**, **uint16**, **uint32**y **uint64**.</span><span class="sxs-lookup"><span data-stu-id="389e9-111">The **Types** drop-down list contains the following predefined variable types: **boolean**, **byte**, **datetime**, **decimal**, **double**, **int16**, **int32**, **int64**, **sbyte**, **single**, **string**, **timespan**, **uint16**, **uint32**, and **uint64**.</span></span> <span data-ttu-id="389e9-112">También puede acceder a los tipos de datos de .NET y las clases seleccionando  **\<.NET clase.. >**, que abrirá el **Seleccionar tipo de artefacto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="389e9-112">You can also access .NET data types and classes by selecting **\<.NET Class...>**, which brings up the **Select Artifact Type** dialog box.</span></span>  
  
4.  <span data-ttu-id="389e9-113">Si selecciona un tipo de variable predefinido, tiene la opción de especificar un valor inicial para la variable.</span><span class="sxs-lookup"><span data-stu-id="389e9-113">If you select a predefined variable type, you have the option of specifying an initial value for the variable.</span></span> <span data-ttu-id="389e9-114">En la ventana Propiedades, establezca la **valor inicial** propiedad.</span><span class="sxs-lookup"><span data-stu-id="389e9-114">In the Properties window, set the **Initial Value** property.</span></span>  
  
     <span data-ttu-id="389e9-115">De otro modo, si el tipo seleccionado es una clase .NET, tiene la opción de usar un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="389e9-115">Otherwise, if the selected type is a .NET class, you have the option of using a default constructor.</span></span> <span data-ttu-id="389e9-116">En la ventana Propiedades, establezca la siguiente propiedad:</span><span class="sxs-lookup"><span data-stu-id="389e9-116">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="389e9-117">Propiedad</span><span class="sxs-lookup"><span data-stu-id="389e9-117">Property</span></span>|<span data-ttu-id="389e9-118">Description</span><span class="sxs-lookup"><span data-stu-id="389e9-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="389e9-119">**Utilizar Constructor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="389e9-119">**Use Default Constructor**</span></span>|<span data-ttu-id="389e9-120">Si se encuentra disponible un constructor predeterminado para una clase .NET, esta propiedad determina si se llamará al constructor predeterminado cuando se use la variable por primera vez:</span><span class="sxs-lookup"><span data-stu-id="389e9-120">If a default constructor is available for a .NET class, this property determines whether the default constructor will be called when you use the variable for the first time:</span></span><br /><br /> <span data-ttu-id="389e9-121">Es true, se llamará al constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="389e9-121">True—The default constructor will be called.</span></span> <span data-ttu-id="389e9-122">Este es el valor predeterminado cuando se encuentre disponible un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="389e9-122">This is the default value when a default constructor is available.</span></span><br /><br /> <span data-ttu-id="389e9-123">False: no se llamará al constructor predeterminado; debe llamar a un constructor en una expresión o realizar una asignación a la variable antes de utilizarla en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="389e9-123">False—The default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="389e9-124">Si el constructor predeterminado requiere parámetros de entrada, puede establecer **utilizar Constructor predeterminado** a **False** y, a continuación, llame al constructor de un **asignación** forma; para ejemplo, `myVariable = myNamespace.myClass (param1, param2)`.</span><span class="sxs-lookup"><span data-stu-id="389e9-124">If the default constructor requires input parameters, you can set **Use Default Constructor** to **False** and then call the constructor from an **Assignment** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="389e9-125">Al agregar una variable a la orquestación, antes de definirla por completo, verá los signos de exclamación en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="389e9-125">When you add a variable to the orchestration, before it is fully defined, you will see exclamation marks in the orchestration.</span></span> <span data-ttu-id="389e9-126">Si elimina esta variable antes de definirla por completo y continúan apareciendo signos de exclamación en la orquestación, puede exigir que la orquestación elimine estos signos de exclamación mediante la creación y eliminación de un parámetro de orquestación.</span><span class="sxs-lookup"><span data-stu-id="389e9-126">If you delete this variable before it is fully defined and the exclamation marks still appear in the orchestration, you can force the orchestration to remove these exclamation marks by creating and then deleting an orchestration parameter.</span></span>  
  
### <a name="to-remove-a-variable"></a><span data-ttu-id="389e9-127">Para quitar una variable</span><span class="sxs-lookup"><span data-stu-id="389e9-127">To remove a variable</span></span>  
  
-   <span data-ttu-id="389e9-128">En la ventana Vista orquestación, haga clic en la variable que desea quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="389e9-128">In the Orchestration View window, right-click the variable you want to remove and then click **Delete**.</span></span>