---
title: "Utilidad de administración de perfiles de cómo implementar perfiles de seguimiento con el seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dde3f351c583be9037127c060d02c98d12b2fcb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a><span data-ttu-id="abacc-102">Cómo implementar perfiles de seguimiento con la utilidad de administración de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="abacc-102">How to Deploy Tracking Profiles with the Tracking Profiles Management Utility</span></span>
<span data-ttu-id="abacc-103">Un gestor empresarial pide a un programador de soluciones que cree un nuevo perfil de seguimiento o que modifique uno ya existente para administrar y supervisar mejor un proceso empresarial específico de la organización.</span><span class="sxs-lookup"><span data-stu-id="abacc-103">A business manager asks a solutions developer to create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span>  
  
 <span data-ttu-id="abacc-104">El programador de soluciones utiliza el Editor de perfiles de seguimiento (TPE) para definir los datos que necesita el analista de negocios.</span><span class="sxs-lookup"><span data-stu-id="abacc-104">The solutions developer uses the Tracking Profile Editor (TPE) to define the data that the business analyst requires.</span></span>  
  
 <span data-ttu-id="abacc-105">Una vez que el programador de soluciones ha creado o modificado el perfil de seguimiento, el administrador usa la utilidad de línea de comandos bttdeploy.exe para implementarlo, para que los cambios se hagan efectivos y se recopilen los datos.</span><span class="sxs-lookup"><span data-stu-id="abacc-105">After a solutions developer creates or modifies the tracking profile, an administrator uses the bttdeploy.exe command line utility to deploy it so that the changes take affect and the data is collected.</span></span> <span data-ttu-id="abacc-106">El programador de soluciones puede implementar los perfiles de seguimiento con el TPE.</span><span class="sxs-lookup"><span data-stu-id="abacc-106">The solutions developer can deploy tracking profiles with the TPE.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="abacc-107">Debe implementar los ensamblados asociados al perfil de seguimiento antes de implementar el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="abacc-107">You must deploy the assemblies associated with the tracking profile before you deploy the tracking profile.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="abacc-108">Deberá disponer de privilegios de administrador de BizTalk® para utilizar esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="abacc-108">You must have BizTalk® Administrator privileges to use this tool.</span></span>  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a><span data-ttu-id="abacc-109">Para implementar el perfil de seguimiento desde la utilidad de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="abacc-109">To deploy the tracking profile from the command-line utility</span></span>  
  
1.  <span data-ttu-id="abacc-110">Desde un símbolo del sistema, desplácese hasta el directorio \<ruta de acceso de instalación\>\Program BizTalk Server \<versión\>\Tracking\\.</span><span class="sxs-lookup"><span data-stu-id="abacc-110">From a command prompt, move to the directory \<installation path\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="abacc-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="abacc-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="abacc-112">Tipo de **bttdeploy.exe \<nombre de perfil\>.btt**.</span><span class="sxs-lookup"><span data-stu-id="abacc-112">Type **bttdeploy.exe \<profile name\>.btt**.</span></span>  
  
3.  <span data-ttu-id="abacc-113">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="abacc-113">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abacc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="abacc-114">See Also</span></span>  
 <span data-ttu-id="abacc-115">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="abacc-115">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="abacc-116">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="abacc-116">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="abacc-117">Supervisión de la actividad económica (BAM)</span><span class="sxs-lookup"><span data-stu-id="abacc-117">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)