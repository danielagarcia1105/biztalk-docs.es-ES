---
title: "Derechos de usuario necesarios para administrar archivos de definición de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb4fb73f-b783-4a04-9bd6-a135b3dd2655
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e39c86eec0cf198a5b879cbc98d29321de71dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="required-user-rights-for-managing-bam-definition-files"></a><span data-ttu-id="9b904-102">Derechos de usuario necesarios para administrar archivos de definición de BAM</span><span class="sxs-lookup"><span data-stu-id="9b904-102">Required User Rights for Managing BAM Definition Files</span></span>
<span data-ttu-id="9b904-103">Los usuarios con cualquier función podrán crear, administrar y ver los archivos de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="9b904-103">BAM definition files can be created, managed, and viewed by users in any role.</span></span> <span data-ttu-id="9b904-104">La administración de archivos de definición de BAM incluye su implementación y eliminación, así como la administración de las actividades, vistas, alertas y artefactos asociados al archivo de definición.</span><span class="sxs-lookup"><span data-stu-id="9b904-104">Managing BAM definition files includes deploying and removing them as well as managing the activities, views, alerts, and artifacts that are associated with the definition file.</span></span>  
  
 <span data-ttu-id="9b904-105">Los administradores deberán mantener una correcta protección de los activos, por ejemplo, creando carpetas compartidas con los permisos de acceso apropiados.</span><span class="sxs-lookup"><span data-stu-id="9b904-105">Administrators should maintain proper asset protection, such as creating shared folders with appropriate access permissions.</span></span> <span data-ttu-id="9b904-106">Al utilizar el complemento de BAM para Excel, se recomienda a los usuarios definir el nivel de seguridad de las macros como “alto”.</span><span class="sxs-lookup"><span data-stu-id="9b904-106">When using the BAM Add-In for Excel, we recommend that users set the macro security level to high.</span></span>  
  
 <span data-ttu-id="9b904-107">No se necesita ningún derecho de usuario para modificar los archivos de definición de BAM (dependiendo de los permisos establecidos en la ubicación de almacenamiento de los archivos de definición en cuestión).</span><span class="sxs-lookup"><span data-stu-id="9b904-107">There are no required user rights needed to modify the BAM definition files (depending on permissions set on where the definition files are stored).</span></span> <span data-ttu-id="9b904-108">Los cambios realizados en los archivos de definición no se aplican automáticamente a la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="9b904-108">Changes to definition files are not automatically applied to the BAM infrastructure.</span></span> <span data-ttu-id="9b904-109">Para aplicar los cambios, deberá usar la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="9b904-109">To apply the changes you must use the BAM Management utility.</span></span>  
  
 <span data-ttu-id="9b904-110">Para usar la utilidad de administración de BAM, deberá ser administrador en el equipo en que se esté aplicando la definición de BAM, o miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9b904-110">To use the BAM Management utility, you must be an administrator on the computer to which the BAM definition is being applied or a member of the BizTalk Server Administrators group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b904-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9b904-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b904-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b904-112">See Also</span></span>  
 <span data-ttu-id="9b904-113">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="9b904-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="9b904-114">[¿Qué es una definición de BAM?](../core/what-is-a-bam-definition.md) </span><span class="sxs-lookup"><span data-stu-id="9b904-114">[What Is a BAM Definition?](../core/what-is-a-bam-definition.md) </span></span>  
 [<span data-ttu-id="9b904-115">Cómo implementar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="9b904-115">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)