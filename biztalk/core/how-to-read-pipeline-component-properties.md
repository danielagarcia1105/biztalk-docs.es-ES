---
title: "Cómo leer las propiedades de componente de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: pipeline components, properties
ms.assetid: 10b1c59c-7ba4-453f-9aaa-1ce9ecf31fac
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19a6ccbcbe7588a0a75b4dbe6bf821a19fab965c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-read-pipeline-component-properties"></a><span data-ttu-id="c4271-102">Cómo leer las propiedades de componente de canalización</span><span class="sxs-lookup"><span data-stu-id="c4271-102">How to Read Pipeline Component Properties</span></span>
<span data-ttu-id="c4271-103">La ventana Propiedades contiene dos secciones para componentes: propiedades generales y propiedades de componentes.</span><span class="sxs-lookup"><span data-stu-id="c4271-103">The Properties window contains two sections for components: general properties and component properties.</span></span> <span data-ttu-id="c4271-104">Las propiedades generales son comunes a todos los componentes, aunque sus valores varíen entre ellos.</span><span class="sxs-lookup"><span data-stu-id="c4271-104">General properties are common to all components, though their values change between components.</span></span>  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a><span data-ttu-id="c4271-105">Para leer las propiedades generales de un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="c4271-105">To read the general properties for a pipeline component</span></span>  
  
1.  <span data-ttu-id="c4271-106">Arrastre el componente de canalización hasta una fase de la canalización o seleccione un componente si ya existe en la canalización.</span><span class="sxs-lookup"><span data-stu-id="c4271-106">Drag the pipeline component into a stage of the pipeline, or select a component if it already exists in the pipeline.</span></span>  
  
2.  <span data-ttu-id="c4271-107">En la ventana Propiedades, en la **General** sección, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c4271-107">In the Properties window, in the **General** section, do the following.</span></span>  
  
    |<span data-ttu-id="c4271-108">Use</span><span class="sxs-lookup"><span data-stu-id="c4271-108">Use this</span></span>|<span data-ttu-id="c4271-109">Para</span><span class="sxs-lookup"><span data-stu-id="c4271-109">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c4271-110">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c4271-110">**Name**</span></span>|<span data-ttu-id="c4271-111">Indica el nombre del componente.</span><span class="sxs-lookup"><span data-stu-id="c4271-111">Indicates the component name.</span></span>|  
    |<span data-ttu-id="c4271-112">**Ensamblado**</span><span class="sxs-lookup"><span data-stu-id="c4271-112">**Assembly**</span></span>|<span data-ttu-id="c4271-113">Indica el ensamblado y la información .NET asociada para el componente.</span><span class="sxs-lookup"><span data-stu-id="c4271-113">Indicates the assembly and associated .NET information for the component.</span></span>|  
    |<span data-ttu-id="c4271-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="c4271-114">**Description**</span></span>|<span data-ttu-id="c4271-115">Indica el nombre descriptivo del componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="c4271-115">Indicates the friendly name of the pipeline component.</span></span>|  
    |<span data-ttu-id="c4271-116">**Administrado**</span><span class="sxs-lookup"><span data-stu-id="c4271-116">**Managed**</span></span>|<span data-ttu-id="c4271-117">Indica si el componente de canalización está administrado o no.</span><span class="sxs-lookup"><span data-stu-id="c4271-117">Indicates whether the pipeline component is managed.</span></span> <span data-ttu-id="c4271-118">**Sí** si el componente es un componente administrado. NET; **n** si el componente de canalización es un componente COM.</span><span class="sxs-lookup"><span data-stu-id="c4271-118">**Yes** if the component is a .NET managed component; **No** if the pipeline component is a COM component.</span></span>|  
    |<span data-ttu-id="c4271-119">**Ruta de acceso**</span><span class="sxs-lookup"><span data-stu-id="c4271-119">**Path**</span></span>|<span data-ttu-id="c4271-120">Indica la ruta de acceso completa al componente .NET.</span><span class="sxs-lookup"><span data-stu-id="c4271-120">Indicates the fully qualified path to the .NET component.</span></span>|  
    |<span data-ttu-id="c4271-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c4271-121">**Type**</span></span>|<span data-ttu-id="c4271-122">Indica el tipo de componente, el ensamblado y la información .NET asociada para el componente.</span><span class="sxs-lookup"><span data-stu-id="c4271-122">Indicates the component type, the assembly, and the associated .NET information for the component.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4271-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4271-123">See Also</span></span>  
 <span data-ttu-id="c4271-124">[Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c4271-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="c4271-125">Crear canalizaciones con el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="c4271-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)