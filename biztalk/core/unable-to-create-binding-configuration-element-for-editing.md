---
title: No se puede crear el elemento de configuración de enlace para su edición | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71853662-5a4a-417e-8160-c93dbcbea336
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5c4387e0cb9287ecc4d491291fdfd1fa6b79ab9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286428"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a><span data-ttu-id="a05e8-102">No se puede crear el elemento de configuración del enlace para su edición</span><span class="sxs-lookup"><span data-stu-id="a05e8-102">Unable to create binding configuration element for editing</span></span>
## <a name="details"></a><span data-ttu-id="a05e8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a05e8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a05e8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a05e8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a05e8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a05e8-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="a05e8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a05e8-106">Event ID</span></span>|<span data-ttu-id="a05e8-107">0</span><span class="sxs-lookup"><span data-stu-id="a05e8-107">0</span></span>|  
|<span data-ttu-id="a05e8-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a05e8-108">Event Source</span></span>|<span data-ttu-id="a05e8-109">0</span><span class="sxs-lookup"><span data-stu-id="a05e8-109">0</span></span>|  
|<span data-ttu-id="a05e8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a05e8-110">Component</span></span>|<span data-ttu-id="a05e8-111">0</span><span class="sxs-lookup"><span data-stu-id="a05e8-111">0</span></span>|  
|<span data-ttu-id="a05e8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a05e8-112">Symbolic Name</span></span>|<span data-ttu-id="a05e8-113">0</span><span class="sxs-lookup"><span data-stu-id="a05e8-113">0</span></span>|  
|<span data-ttu-id="a05e8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a05e8-114">Message Text</span></span>|<span data-ttu-id="a05e8-115">No se puede crear el elemento de configuración del enlace para su edición.</span><span class="sxs-lookup"><span data-stu-id="a05e8-115">Unable to create binding configuration element for editing.</span></span> <span data-ttu-id="a05e8-116">Compruebe los valores de las propiedades BindingType y BindingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a05e8-116">Check the values of the BindingType and BindingConfiguration properties.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a05e8-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="a05e8-117">Explanation</span></span>  
 <span data-ttu-id="a05e8-118">Se produjo un error al cargar un elemento de enlace para visualizarlo en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a05e8-118">There was an error loading a binding element for display in the user interface.</span></span> <span data-ttu-id="a05e8-119">Este error se produce con frecuencia con los enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="a05e8-119">This error often occurs with custom binding.</span></span> <span data-ttu-id="a05e8-120">Probablemente falta el elemento de enlace en el archivo de configuración y, por lo tanto, no está disponible en la lista desplegable para el enlace.</span><span class="sxs-lookup"><span data-stu-id="a05e8-120">The binding element is probably missing in the configuration file and is therefore not available on the drop-down list for binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a05e8-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a05e8-121">User Action</span></span>  
 <span data-ttu-id="a05e8-122">Compruebe los valores de la **BindingType** y **BindingConfiguration** propiedades.</span><span class="sxs-lookup"><span data-stu-id="a05e8-122">Check the values of the **BindingType** and **BindingConfiguration** properties.</span></span>  
  
 <span data-ttu-id="a05e8-123">Para obtener más información sobre la creación de elementos de configuración de enlace, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="a05e8-123">For further information on creating binding configuration elements, see the following resource:</span></span>  
  
-   [<span data-ttu-id="a05e8-124">Configurar el adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="a05e8-124">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)