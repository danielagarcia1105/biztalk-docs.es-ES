---
title: Anular la implementación de aplicaciones de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeploying, applications
- applications, undeploying
- managing [applications], undeploying
- undeploying
ms.assetid: 424ada20-d023-4952-8a36-75f0327d87d5
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1d8756eee08b2d4034c90efd638934ef0511ac1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286644"
---
# <a name="undeploying-biztalk-applications"></a><span data-ttu-id="457d2-102">Anular la implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="457d2-102">Undeploying BizTalk Applications</span></span>
<span data-ttu-id="457d2-103">Debe anular la implementación de una aplicación de BizTalk para poder quitarla de su grupo de BizTalk y de los equipos host.</span><span class="sxs-lookup"><span data-stu-id="457d2-103">You must undeploy a BizTalk application to remove it from your BizTalk group and host computers.</span></span> <span data-ttu-id="457d2-104">En esta sección se describen las siguientes tareas que forman parte de la anulación de implementación de una aplicación:</span><span class="sxs-lookup"><span data-stu-id="457d2-104">This section describes the following tasks involved in undeploying an application:</span></span>  
  
-   <span data-ttu-id="457d2-105">**Eliminar la aplicación de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="457d2-105">**Delete the BizTalk application.**</span></span> <span data-ttu-id="457d2-106">se quitan sus datos de las bases de datos de BizTalk para el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="457d2-106">This removes its data from the BizTalk databases for the BizTalk group.</span></span> <span data-ttu-id="457d2-107">Cuando lo haga, la aplicación ya no se mostrará más en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="457d2-107">When you do this, the application no longer displays in the BizTalk Administration console.</span></span>  
  
-   <span data-ttu-id="457d2-108">**Desinstale la aplicación de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="457d2-108">**Uninstall the BizTalk application.**</span></span>  <span data-ttu-id="457d2-109">se quitan los archivos y la configuración asociados a la aplicación, así como sus artefactos, del sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="457d2-109">This removes the files and settings associated with the application and its artifacts from the local file system.</span></span>  
  
-   <span data-ttu-id="457d2-110">**Quitar otros archivos y configuraciones.**</span><span class="sxs-lookup"><span data-stu-id="457d2-110">**Removing other files and settings.**</span></span> <span data-ttu-id="457d2-111">quizás sea necesario quitar otros archivos y configuraciones asociados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="457d2-111">You may also need to remove certain other files and settings associated with the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="457d2-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="457d2-112">In This Section</span></span>  
  
-   [<span data-ttu-id="457d2-113">Cómo eliminar una aplicación de BizTalk del grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="457d2-113">How to Delete a BizTalk Application from the BizTalk Group</span></span>](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)  
  
-   [<span data-ttu-id="457d2-114">Cómo desinstalar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="457d2-114">How to Uninstall a BizTalk Application</span></span>](../core/how-to-uninstall-a-biztalk-application.md)  
  
-   [<span data-ttu-id="457d2-115">Cómo quitar otros archivos y configuraciones para una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="457d2-115">How to Remove Other Files and Settings for a BizTalk Application</span></span>](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)