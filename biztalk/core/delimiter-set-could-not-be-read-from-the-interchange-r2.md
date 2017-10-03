---
title: No se pudo leer el conjunto de delimitadores del intercambio (R2) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17bdd32e-d43f-4f59-af27-5d3054fd5432
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3836b218ac3596bef25edb29eaf72c38f65b6e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a><span data-ttu-id="89977-102">No se pudo leer el conjunto de delimitadores del intercambio (R2)</span><span class="sxs-lookup"><span data-stu-id="89977-102">Delimiter set could not be read from the interchange (R2)</span></span>
## <a name="details"></a><span data-ttu-id="89977-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="89977-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89977-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="89977-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="89977-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="89977-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="89977-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="89977-106">Event ID</span></span>|-|  
|<span data-ttu-id="89977-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="89977-107">Event Source</span></span>|<span data-ttu-id="89977-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89977-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="89977-109">Componente</span><span class="sxs-lookup"><span data-stu-id="89977-109">Component</span></span>|<span data-ttu-id="89977-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="89977-110">EDI Engine</span></span>|  
|<span data-ttu-id="89977-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="89977-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="89977-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="89977-112">Message Text</span></span>|<span data-ttu-id="89977-113">No se pudo leer el conjunto de delimitadores del intercambio.</span><span class="sxs-lookup"><span data-stu-id="89977-113">Delimiter set could not be read from the interchange.</span></span> <span data-ttu-id="89977-114">Falta el atributo DelimiterSetSerializedData en el nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="89977-114">The attribute DelimiterSetSerializedData is missing from root node.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="89977-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="89977-115">Explanation</span></span>  
 <span data-ttu-id="89977-116">Este error indica que el intercambio no contiene los valores del conjunto de delimitadores.</span><span class="sxs-lookup"><span data-stu-id="89977-116">This error indicates the interchange does not contain the delimiter set values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89977-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="89977-117">User Action</span></span>  
 <span data-ttu-id="89977-118">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="89977-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="89977-119">Agregue valores del conjunto de delimitadores al intercambio, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="89977-119">Add delimiter set values to the interchange, as follows:</span></span>  
  
    1.  <span data-ttu-id="89977-120">Abra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="89977-120">Open up the message.</span></span>  
  
    2.  <span data-ttu-id="89977-121">Determine si hay un segmento UNA en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="89977-121">Determine whether there is a UNA segment in the interchange.</span></span> <span data-ttu-id="89977-122">Si no hay ningún segmento UNA, pida al socio que lo agregue al intercambio.</span><span class="sxs-lookup"><span data-stu-id="89977-122">If there is not a UNA segment, ask the partner to add the UNA segment to the interchange.</span></span>  
  
-   <span data-ttu-id="89977-123">Escriba los valores del delimitador en la propiedad de canalización EfactDelimiters, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="89977-123">Enter the delimiter values to the EfactDelimiters pipeline property, as follows:</span></span>  
  
    1.  <span data-ttu-id="89977-124">En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], haga clic con el botón secundario en la ubicación de recepción o puerto de envío mediante la canalización para la que desee establecer las propiedades.</span><span class="sxs-lookup"><span data-stu-id="89977-124">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="89977-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="89977-125">Click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="89977-126">Haga clic en el botón de elipsis (…) junto a la canalización para la que desee establecer las propiedades.</span><span class="sxs-lookup"><span data-stu-id="89977-126">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
    3.  <span data-ttu-id="89977-127">Escriba valores para los delimitadores de UNA como una lista delimitada por comas (para UNA1, UNA2, UNA3, UNA4, UNA5 y UNA6), y cambie los valores predeterminados según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="89977-127">Enter values for the UNA delimiters as a comma-delimited list (for UNA1, UNA2, UNA3, UNA4, UNA5, and UNA6), changing the defaults as required.</span></span> <span data-ttu-id="89977-128">Los valores predeterminados son los siguientes: 0x3A, 0x2B, 0x2C, 0x3F, 0 x 20, 0 x 27.</span><span class="sxs-lookup"><span data-stu-id="89977-128">The defaults are as follows: 0x3A, 0x2B, 0x2C, 0x3F, 0x20, 0x27.</span></span>  
  
    4.  <span data-ttu-id="89977-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89977-129">Click **OK**.</span></span>