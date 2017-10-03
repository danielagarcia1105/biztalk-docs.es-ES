---
title: "Cómo configurar tipos de correlaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 646ac7dafd5207a2558e45252077efe2d9616a70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-types"></a><span data-ttu-id="0b1ae-102">Cómo configurar tipos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="0b1ae-102">How to Configure Correlation Types</span></span>
<span data-ttu-id="0b1ae-103">Usa el **propiedades de correlación** cuadro de diálogo para agregar o quitar propiedades de un tipo de correlación.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-103">You use the **Correlation Properties** dialog box to add or remove properties from a correlation type.</span></span> <span data-ttu-id="0b1ae-104">El tipo de correlación enumera las propiedades de un conjunto de correlaciones que utilizan las actividades de envío y recepción para garantizar que los mensajes entrantes se correlacionan correctamente con las instancias correctas de una orquestación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-104">The correlation type lists the properties in a correlation set which are used by Send and Receive activities to make sure that incoming messages are properly correlated with the right instances of an orchestration at run time.</span></span>  
  
 <span data-ttu-id="0b1ae-105">Hay dos paneles en el cuadro de diálogo, cada uno con una lista de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-105">There are two panes in the dialog box, each containing a list of properties.</span></span> <span data-ttu-id="0b1ae-106">El panel izquierdo, "Propiedades disponibles", contiene una vista de árbol de todas las propiedades definidas en el proyecto o a las que se hace referencia en el mismo.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-106">The left pane, "Available Properties", contains a tree view of all of the properties that are defined in your project or referenced by it.</span></span> <span data-ttu-id="0b1ae-107">Las propiedades que aparecen de forma predeterminada son propiedades del sistema, definidas por BizTalk Server, aunque también puede definir sus propias propiedades en un esquema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-107">The properties that appear by default are system properties, defined by BizTalk Server, but you can also define your own properties in a property schema.</span></span> <span data-ttu-id="0b1ae-108">Para obtener más información acerca de cómo crear esquemas de propiedades, vea [esquemas de propiedades](../core/property-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="0b1ae-108">For more information about creating property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b1ae-109">Las propiedades de esquema deben estar promocionadas antes de poder usarlas en un tipo de correlación.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-109">Schema properties must be promoted before they can be used in a correlation type.</span></span> <span data-ttu-id="0b1ae-110">Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0b1ae-110">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
### <a name="to-add-and-configure-a-correlation-type"></a><span data-ttu-id="0b1ae-111">Para agregar y configurar un tipo de correlación</span><span class="sxs-lookup"><span data-stu-id="0b1ae-111">To add and configure a correlation type</span></span>  
  
-   <span data-ttu-id="0b1ae-112">En la ventana Vista orquestación, haga clic en **tipos de correlaciones** y, a continuación, haga clic en **nuevo tipo de correlación**.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-112">In the Orchestration View window, right-click **Correlation Types** and then click **New Correlation Type**.</span></span>  
  
     <span data-ttu-id="0b1ae-113">El **propiedades de correlación** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-113">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="0b1ae-114">Agregue las propiedades que desee incluir en el tipo de correlación.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-114">Add properties that you want to include in your correlation type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b1ae-115">Si tiene acceso a la **propiedades de correlación** cuadro de diálogo directamente desde una correlación del conjunto, se crea un tipo de correlación para el conjunto de correlaciones si no existe.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-115">If you access the **Correlation Properties** dialog box directly from a correlation set, a correlation type for the correlation set is created if one does not already exist.</span></span> <span data-ttu-id="0b1ae-116">Los cambios realizados se guardarán en el nuevo tipo de correlación, y se configurará el conjunto de correlaciones para que utilice este nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-116">Your changes will be saved to the new correlation type, and the correlation set will be configured to use the new correlation type.</span></span> <span data-ttu-id="0b1ae-117">Si el tipo de correlación ya existe en el conjunto de correlaciones y realiza algún cambio, se modificará el tipo de correlación.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-117">If a correlation type already existed for the correlation set and you make changes, the correlation type will be modified.</span></span>  
  
### <a name="to-remove-a-correlation-type"></a><span data-ttu-id="0b1ae-118">Para quitar un tipo de correlación</span><span class="sxs-lookup"><span data-stu-id="0b1ae-118">To remove a correlation type</span></span>  
  
-   <span data-ttu-id="0b1ae-119">En la ventana Vista orquestación, haga clic en el tipo de correlación que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0b1ae-119">In the Orchestration View window, right-click the correlation type you want to remove and then click **Delete**.</span></span>