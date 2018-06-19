---
title: Errores de acción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87cf0a5b-d1dd-4807-9660-e8a8b7012b40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f25f1f15307077943ef370a335885690bea22c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225596"
---
# <a name="action-errors"></a><span data-ttu-id="a6803-102">Errores de acción</span><span class="sxs-lookup"><span data-stu-id="a6803-102">Action Errors</span></span>
<span data-ttu-id="a6803-103">En esta sección se incluye información detallada para diagnosticar y resolver errores de acciones de WCF.</span><span class="sxs-lookup"><span data-stu-id="a6803-103">This section contains detailed information for diagnosing and resolving WCF Action errors.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6803-104">Detalles</span><span class="sxs-lookup"><span data-stu-id="a6803-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6803-105">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a6803-105">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a6803-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a6803-106">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="a6803-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a6803-107">Event ID</span></span>|<span data-ttu-id="a6803-108">0</span><span class="sxs-lookup"><span data-stu-id="a6803-108">0</span></span>|  
|<span data-ttu-id="a6803-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a6803-109">Event Source</span></span>|<span data-ttu-id="a6803-110">0</span><span class="sxs-lookup"><span data-stu-id="a6803-110">0</span></span>|  
|<span data-ttu-id="a6803-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a6803-111">Component</span></span>|<span data-ttu-id="a6803-112">0</span><span class="sxs-lookup"><span data-stu-id="a6803-112">0</span></span>|  
|<span data-ttu-id="a6803-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a6803-113">Symbolic Name</span></span>|<span data-ttu-id="a6803-114">0</span><span class="sxs-lookup"><span data-stu-id="a6803-114">0</span></span>|  
|<span data-ttu-id="a6803-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a6803-115">Message Text</span></span>|<span data-ttu-id="a6803-116">Una acción única no puede contener caracteres de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="a6803-116">A single action cannot contain new line characters.</span></span> <span data-ttu-id="a6803-117">Quite todos los caracteres de nueva línea,</span><span class="sxs-lookup"><span data-stu-id="a6803-117">Remove all new line characters.</span></span> <span data-ttu-id="a6803-118">o use la sintaxis de asignación de acción para especificar varias acciones.</span><span class="sxs-lookup"><span data-stu-id="a6803-118">Or, to specify multiple actions, use the action mapping syntax.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6803-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="a6803-119">Explanation</span></span>  
 <span data-ttu-id="a6803-120">Este error indica que la propiedad de acción de un puerto de envío contiene un carácter de nueva línea, que no está permitido.</span><span class="sxs-lookup"><span data-stu-id="a6803-120">This error indicates the action property of a send port contains a new line character, which is not allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6803-121">Esta restricción no se aplica cuando la acción se define como una asignación.</span><span class="sxs-lookup"><span data-stu-id="a6803-121">This restriction does not apply when the action is defined as a mapping.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6803-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a6803-122">User Action</span></span>  
 <span data-ttu-id="a6803-123">Use el procedimiento siguiente para corregir la propiedad de la acción.</span><span class="sxs-lookup"><span data-stu-id="a6803-123">Use the following procedure to fix the action property.</span></span>  
  
 
1.  <span data-ttu-id="a6803-124">Abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a6803-124">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a6803-125">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6803-125">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="a6803-126">Localice la aplicación y, a continuación, el transporte.</span><span class="sxs-lookup"><span data-stu-id="a6803-126">Locate your application, and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="a6803-127">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="a6803-127">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="a6803-128">Seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a6803-128">Select **Properties**.</span></span>  
  
6.  <span data-ttu-id="a6803-129">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="a6803-129">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="a6803-130">Seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a6803-130">Select **Configure**.</span></span>  
  
8.  <span data-ttu-id="a6803-131">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, seleccione la **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="a6803-131">In the **WCF [***transport type***] Transport Properties** dialog box, select the **General** tab.</span></span>  
  
9. <span data-ttu-id="a6803-132">En el **encabezado de acción SOAP** sección, quite el carácter de nueva línea de la **acción** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="a6803-132">In the **SOAP Action header** section, remove the new line character from the **Action** text box.</span></span>  

## <a name="more-good-info"></a><span data-ttu-id="a6803-133">Más información válida</span><span class="sxs-lookup"><span data-stu-id="a6803-133">More good info</span></span>  
 <span data-ttu-id="a6803-134">Para obtener más información sobre las acciones, vea [especificar acciones SOAP para adaptadores de envío de WCF](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span><span class="sxs-lookup"><span data-stu-id="a6803-134">For additional information on actions, see [Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span></span>