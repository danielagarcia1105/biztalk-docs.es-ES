---
title: "Forma reglas de cómo utilizar la llamada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85badfaf22ff4fb6aebd9ed19c757faaa1f303c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-use-the-call-rules-shape"></a><span data-ttu-id="89712-102">Cómo usar la forma Reglas de llamada</span><span class="sxs-lookup"><span data-stu-id="89712-102">How to Use the Call Rules Shape</span></span>
<span data-ttu-id="89712-103">En el Diseñador de orquestaciones, puede usar el **reglas de llamada** forma para llamar a una directiva empresarial.</span><span class="sxs-lookup"><span data-stu-id="89712-103">In Orchestration Designer, you can use the **Call Rules** shape to call a business policy.</span></span>  
  
### <a name="to-configure-the-call-rules-shape"></a><span data-ttu-id="89712-104">Para configurar la forma Reglas de llamada</span><span class="sxs-lookup"><span data-stu-id="89712-104">To configure the Call Rules shape</span></span>  
  
1.  <span data-ttu-id="89712-105">En el cuadro de herramientas, en la **orquestaciones de BizTalk** ficha, arrastre el **reglas de llamada** forma en una línea de conexión en la superficie de diseño de orquestación.</span><span class="sxs-lookup"><span data-stu-id="89712-105">From the Toolbox, in the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
     <span data-ttu-id="89712-106">: "O":</span><span class="sxs-lookup"><span data-stu-id="89712-106">—Or—</span></span>  
  
     <span data-ttu-id="89712-107">Haga clic en la línea de conexión o el marcador de posición de la forma en la que desea agregar la forma, seleccione **Insertar forma** en el menú contextual y, a continuación, haga clic en **reglas de llamada**.</span><span class="sxs-lookup"><span data-stu-id="89712-107">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape** on the context menu, and then click **Call Rules**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="89712-108">En BizTalk Server, no es necesario tener un ámbito atómico para insertar un **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="89712-108">In BizTalk Server, you do not need to have an atomic scope to insert a **Call Rules** shape.</span></span> <span data-ttu-id="89712-109">Puede arrastrar una **reglas de llamada** forma en la superficie de diseño de orquestación en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="89712-109">You can drag a **Call Rules** shape into the Orchestration Design Surface from the Toolbox.</span></span> <span data-ttu-id="89712-110">Sin embargo, en el servidor BizTalk Server, el **reglas de llamada** elemento de menú está deshabilitado en el menú contextual si se intenta insertar un **reglas de llamada** forma dentro de una orquestación que no tiene un ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="89712-110">However, in BizTalk Server, the **Call Rules** menu item is disabled in the context menu if you try to insert a **Call Rules** shape inside an orchestration that does not have an atomic scope.</span></span> <span data-ttu-id="89712-111">Ésta es una limitación del producto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89712-111">This is a limitation with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product.</span></span>  
  
2.  <span data-ttu-id="89712-112">En el Diseñador de orquestaciones, seleccione la **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="89712-112">In Orchestration Designer, select the **Call Rules** shape.</span></span>  
  
3.  <span data-ttu-id="89712-113">Haga doble clic en la forma que se va a mostrar el **configuración de directiva CallRules** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="89712-113">Double-click the shape to display the **CallRules policy configuration** dialog box.</span></span>  
  
4.  <span data-ttu-id="89712-114">En el **seleccione la directiva empresarial que se va a llamar a** lista desplegable, seleccione la directiva que necesite.</span><span class="sxs-lookup"><span data-stu-id="89712-114">In the **Select the business policy you wish to call** drop-down list, select the policy you need.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="89712-115">La configuración de directivas de Reglas de llamada se fijará en la última versión guardada de una directiva para determinar los tipos que se han utilizado en ésta.</span><span class="sxs-lookup"><span data-stu-id="89712-115">Call Rules configuration will look at the latest saved version of a policy when determining the types used in the policy.</span></span> <span data-ttu-id="89712-116">En tiempo de ejecución, se utilizará la última versión implementada de la directiva.</span><span class="sxs-lookup"><span data-stu-id="89712-116">At run time, the latest deployed version of the policy will be used.</span></span>  
  
5.  <span data-ttu-id="89712-117">En el **especificar parámetros de la directiva** cuadro de lista, seleccione una variable de la **nombre de parámetro** propiedad.</span><span class="sxs-lookup"><span data-stu-id="89712-117">In the **Specify policy parameters** list box, select a variable from the **Parameter Name** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="89712-118">El **reglas de llamada** forma básicamente reconstruye el mensaje, como si utilizara una **construir** forma, que a su vez puede provocar que las propiedades de contexto del mensaje se perderán.</span><span class="sxs-lookup"><span data-stu-id="89712-118">The **Call Rules** shape is essentially reconstructing the message, as if using a **Construct** shape, which in turn may cause context properties of the message to be lost.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="89712-119">Puede especificar un mensaje o una variable de .NET como un parámetro a una directiva del BRE.</span><span class="sxs-lookup"><span data-stu-id="89712-119">You can specify a message or a .NET variable as a parameter to a BRE policy.</span></span> <span data-ttu-id="89712-120">Para pasar un **TypedXmlDocument** hecho, especifique el mensaje correspondiente declarado en la orquestación como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="89712-120">To pass a **TypedXmlDocument** fact, specify the corresponding message declared in the orchestration as a parameter.</span></span> <span data-ttu-id="89712-121">Para pasar un hecho de .NET, especifique una variable de .NET declarada en la orquestación como parámetro.</span><span class="sxs-lookup"><span data-stu-id="89712-121">To pass a .NET fact, specify a .NET variable declared in the orchestration as a parameter.</span></span> <span data-ttu-id="89712-122">Para pasar un hecho de base de datos, especifique una variable de .NET de tipo **DataConnection** o **TypedDataTable** como un parámetro a la directiva.</span><span class="sxs-lookup"><span data-stu-id="89712-122">To pass a database fact, specify a .NET variable of type **DataConnection** or **TypedDataTable** as a parameter to the policy.</span></span>