---
title: No se puede crear el elemento de configuración de enlace para su edición | Microsoft Docs
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
ms.openlocfilehash: 98e58ec9966d0e0534d078fc5741f267bf02e735
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974341"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a><span data-ttu-id="b4b2f-102">No se puede crear el elemento de configuración del enlace para su edición</span><span class="sxs-lookup"><span data-stu-id="b4b2f-102">Unable to create binding configuration element for editing</span></span>
## <a name="details"></a><span data-ttu-id="b4b2f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b4b2f-103">Details</span></span>  
  
|                 |                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b4b2f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b4b2f-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="b4b2f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b4b2f-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                      |
|    <span data-ttu-id="b4b2f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b4b2f-106">Event ID</span></span>     |                                                                  <span data-ttu-id="b4b2f-107">0</span><span class="sxs-lookup"><span data-stu-id="b4b2f-107">0</span></span>                                                                   |
|  <span data-ttu-id="b4b2f-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b4b2f-108">Event Source</span></span>   |                                                                  <span data-ttu-id="b4b2f-109">0</span><span class="sxs-lookup"><span data-stu-id="b4b2f-109">0</span></span>                                                                   |
|    <span data-ttu-id="b4b2f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b4b2f-110">Component</span></span>    |                                                                  <span data-ttu-id="b4b2f-111">0</span><span class="sxs-lookup"><span data-stu-id="b4b2f-111">0</span></span>                                                                   |
|  <span data-ttu-id="b4b2f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b4b2f-112">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="b4b2f-113">0</span><span class="sxs-lookup"><span data-stu-id="b4b2f-113">0</span></span>                                                                   |
|  <span data-ttu-id="b4b2f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b4b2f-114">Message Text</span></span>   | <span data-ttu-id="b4b2f-115">No se puede crear el elemento de configuración del enlace para su edición.</span><span class="sxs-lookup"><span data-stu-id="b4b2f-115">Unable to create binding configuration element for editing.</span></span> <span data-ttu-id="b4b2f-116">Compruebe los valores de las propiedades BindingType y BindingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b4b2f-116">Check the values of the BindingType and BindingConfiguration properties.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b4b2f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b4b2f-117">Explanation</span></span>  
 <span data-ttu-id="b4b2f-118">Se produjo un error al cargar un elemento de enlace para visualizarlo en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4b2f-118">There was an error loading a binding element for display in the user interface.</span></span> <span data-ttu-id="b4b2f-119">Este error se produce con frecuencia con los enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="b4b2f-119">This error often occurs with custom binding.</span></span> <span data-ttu-id="b4b2f-120">Probablemente falta el elemento de enlace en el archivo de configuración y, por lo tanto, no está disponible en la lista desplegable para el enlace.</span><span class="sxs-lookup"><span data-stu-id="b4b2f-120">The binding element is probably missing in the configuration file and is therefore not available on the drop-down list for binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4b2f-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b4b2f-121">User Action</span></span>  
 <span data-ttu-id="b4b2f-122">Compruebe los valores de la **BindingType** y **BindingConfiguration** propiedades.</span><span class="sxs-lookup"><span data-stu-id="b4b2f-122">Check the values of the **BindingType** and **BindingConfiguration** properties.</span></span>  
  
 <span data-ttu-id="b4b2f-123">Para obtener más información sobre la creación de elementos de configuración de enlace, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4b2f-123">For further information on creating binding configuration elements, see the following resource:</span></span>  
  
-   [<span data-ttu-id="b4b2f-124">Configuración del adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="b4b2f-124">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)