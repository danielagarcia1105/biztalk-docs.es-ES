---
title: "Utilidad de implementación de perfil de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c4d261069b83741413e255a3f8bacd6dd9260d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-profile-deployment-utility"></a><span data-ttu-id="451b8-102">Utilidad de implementación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="451b8-102">Tracking Profile Deployment Utility</span></span>
<span data-ttu-id="451b8-103">Los programadores emplean la utilidad bttdeploy para aplicar perfiles de seguimiento y quitarlos de la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="451b8-103">Developers use the bttdeploy utility to apply tracking profiles to and remove them from the BAM infrastructure.</span></span> <span data-ttu-id="451b8-104">Usar la utilidad bttdeploy equivale funcionalmente a hacer clic en la opción del menú Aplicar perfil de seguimiento del Editor de perfiles de seguimiento (TPE).</span><span class="sxs-lookup"><span data-stu-id="451b8-104">Using the bttdeploy utility is functionally equivalent to clicking the Apply Tracking Profile menu option in the Tracking Profile Editor (TPE).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="451b8-105">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="451b8-105">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="451b8-106">**Uso**</span><span class="sxs-lookup"><span data-stu-id="451b8-106">**Usage**</span></span>  
  
 <span data-ttu-id="451b8-107">**nombre de archivo BttDeploy.exe [opciones]**</span><span class="sxs-lookup"><span data-stu-id="451b8-107">**bttdeploy.exe [options] file name**</span></span>  
  
|<span data-ttu-id="451b8-108">Opción</span><span class="sxs-lookup"><span data-stu-id="451b8-108">Option</span></span>|<span data-ttu-id="451b8-109">Description</span><span class="sxs-lookup"><span data-stu-id="451b8-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="451b8-110">/h o /?</span><span class="sxs-lookup"><span data-stu-id="451b8-110">/h or /?</span></span>|<span data-ttu-id="451b8-111">Opcional: Muestra la sintaxis de resumen para bttdeploy.</span><span class="sxs-lookup"><span data-stu-id="451b8-111">Optional: Displays the syntax summary for bttdeploy.</span></span>|  
|<span data-ttu-id="451b8-112">/mgdb \<nombre del servidor [, puerto] >\\< nombre de base de datos\></span><span class="sxs-lookup"><span data-stu-id="451b8-112">/mgdb \<server name[,port]>\\<database name\></span></span>|<span data-ttu-id="451b8-113">Opcional: Especifica el servidor de administración, el puerto y el nombre de la base de datos que se va a aplicar el perfil.</span><span class="sxs-lookup"><span data-stu-id="451b8-113">Optional: Specifies the management server, port, and database name to which to apply the profile.</span></span> <span data-ttu-id="451b8-114">**Nota:** cuando se usa este parámetro, el puerto es opcional.</span><span class="sxs-lookup"><span data-stu-id="451b8-114">**Note:**  When using this parameter, the port is optional.</span></span>|  
|<span data-ttu-id="451b8-115">/quitar</span><span class="sxs-lookup"><span data-stu-id="451b8-115">/remove</span></span>|<span data-ttu-id="451b8-116">Opcional: Especifica que el perfil de seguimiento se quitará de la base de datos BAM.</span><span class="sxs-lookup"><span data-stu-id="451b8-116">Optional: Specifies that the tracking profile is to be removed from the BAM database.</span></span>|  
|<span data-ttu-id="451b8-117">filename</span><span class="sxs-lookup"><span data-stu-id="451b8-117">filename</span></span>|<span data-ttu-id="451b8-118">Nombre del archivo de perfil de seguimiento que se va a aplicar o quitar.</span><span class="sxs-lookup"><span data-stu-id="451b8-118">The name of the tracking profile file to apply or remove.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="451b8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="451b8-119">See Also</span></span>  
 <span data-ttu-id="451b8-120">[Editor de perfiles de seguimiento](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="451b8-120">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="451b8-121">Cómo quitar perfiles de seguimiento huérfanos</span><span class="sxs-lookup"><span data-stu-id="451b8-121">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)