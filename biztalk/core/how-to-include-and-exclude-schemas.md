---
title: "Cómo incluir y excluir esquemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9206458-e5d6-48d7-87a6-9471ba60dca7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfa1f610cef6e67f17ca14737c6ca853dd5cd16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-include-and-exclude-schemas"></a><span data-ttu-id="d2fa1-102">Cómo incluir y excluir esquemas</span><span class="sxs-lookup"><span data-stu-id="d2fa1-102">How to Include and Exclude Schemas</span></span>
<span data-ttu-id="d2fa1-103">Un archivo de esquema puede estar presente en una carpeta de proyecto de BizTalk, pero no incluirse en ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-103">A schema file can exist in a BizTalk project folder and not be included in that project.</span></span> <span data-ttu-id="d2fa1-104">En ese caso, se dice que el esquema se puede excluir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-104">Such a schema is said to be excluded from the project.</span></span> <span data-ttu-id="d2fa1-105">Los esquemas excluidos no se compilan cuando se genera el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-105">Excluded schemas are not compiled when you build the BizTalk project.</span></span> <span data-ttu-id="d2fa1-106">Este tema describe los pasos necesarios para incluir un esquema excluido en un proyecto de BizTalk, así como para excluir un esquema de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-106">This topic describes the steps required to include an excluded schema in a BizTalk project, and to exclude a schema from a BizTalk project.</span></span>  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a><span data-ttu-id="d2fa1-107">Para incluir un esquema en un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d2fa1-107">To include a schema in a BizTalk project</span></span>  
  
1.  <span data-ttu-id="d2fa1-108">En el Explorador de soluciones, abra el proyecto de BizTalk que contiene el esquema que va a incluir en la carpeta de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-108">In Solution Explorer, open the BizTalk project that contains the schema to be included in its project folder.</span></span>  
  
2.  <span data-ttu-id="d2fa1-109">Si todos los archivos no se muestran, en la **proyecto** menú, haga clic en **mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-109">If all files are not already showing, on the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="d2fa1-110">En el Explorador de soluciones, haga clic en el esquema excluido que desea incluir y, a continuación, haga clic en **incluir en el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-110">In Solution Explorer, right-click the excluded schema that you want to include, and then click **Include In Project**.</span></span>  
  
     <span data-ttu-id="d2fa1-111">El icono del esquema excluido anteriormente en el Explorador de soluciones cambia de un esquema vacío a un icono de esquema normal.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-111">The icon for the previously excluded schema in Solution Explorer changes from an empty outline to the normal schema icon.</span></span>  
  
4.  <span data-ttu-id="d2fa1-112">Si lo desea, en la **proyecto** menú, haga clic en **mostrar todos los archivos** para ocultar todos los archivos en la carpeta del proyecto que no están incluidos en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-112">Optionally, on the **Project** menu, click **Show All Files** to hide all files in the project folder that are not included in the project.</span></span>  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a><span data-ttu-id="d2fa1-113">Para excluir un esquema de un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d2fa1-113">To exclude a schema from a BizTalk project</span></span>  
  
-   <span data-ttu-id="d2fa1-114">En el Explorador de soluciones, haga clic en el esquema que desea excluir y, a continuación, haga clic en **excluir del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-114">In Solution Explorer, right-click the schema that you want to exclude, and then click **Exclude From Project**.</span></span>  
  
     <span data-ttu-id="d2fa1-115">El esquema se excluye del proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-115">The schema is now excluded from the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2fa1-116">Al excluir un esquema de un proyecto, éste no se quita del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-116">When you exclude a schema from a project, the schema is not removed from the file system.</span></span> <span data-ttu-id="d2fa1-117">Sin embargo, el esquema no se incluye al generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-117">However, the schema is not included when you build the project.</span></span> <span data-ttu-id="d2fa1-118">Puede elegir si se debe o no mostrar archivos excluidos en la carpeta del proyecto, cambie la **mostrar todos los archivos** herramienta en la parte superior de la ventana Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-118">You can choose whether or not to display excluded files in the project folder by toggling the **Show All Files** tool at the top of the Solution Explorer window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2fa1-119">Si desea eliminar el esquema del sistema de archivos, así como quitar el archivo de esquema del proyecto, debe eliminar el esquema.</span><span class="sxs-lookup"><span data-stu-id="d2fa1-119">If you want to delete the schema from the file system as well as removing the schema file from the project, you need to delete the schema.</span></span> <span data-ttu-id="d2fa1-120">Para obtener más información acerca de cómo eliminar esquemas, vea [eliminar esquemas](../core/how-to-delete-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="d2fa1-120">For more information about deleting schemas, see [Deleting Schemas](../core/how-to-delete-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2fa1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2fa1-121">See Also</span></span>  
 [<span data-ttu-id="d2fa1-122">Administrar esquemas en proyectos</span><span class="sxs-lookup"><span data-stu-id="d2fa1-122">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)