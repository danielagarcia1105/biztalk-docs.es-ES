---
title: Derechos de usuario para administrar el TPE | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, Tracking Profile Editor
- Tracking Profile Editor, security
ms.assetid: a0353c4d-2aaa-49ac-8e50-88885962abba
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3319a807b1357201dade0c53d04c26146c2b1e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="user-rights-for-managing-tpe"></a><span data-ttu-id="5b93e-102">Derechos de usuario para administrar el TPE</span><span class="sxs-lookup"><span data-stu-id="5b93e-102">User Rights for Managing TPE</span></span>
<span data-ttu-id="5b93e-103">Los programadores de soluciones, los administradores del sistema o el personal de operaciones y TI deben disponer de derechos administrativos para recuperar o implementar el perfil de seguimiento en la base de datos asociada al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b93e-103">Solution developers, system administrators, or IT/Operations personnel must have administrative rights to retrieve or deploy the tracking profile into a database associated with an assembly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5b93e-104">No puede definir roles de usuario ni conceder o denegar permisos utilizando el Editor de perfiles de seguimiento (TPE).</span><span class="sxs-lookup"><span data-stu-id="5b93e-104">You cannot define user roles or grant or deny user permissions using Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="5b93e-105">Solo podrá definir estos roles de usuario y los permisos asociados en Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b93e-105">You can only define these user roles and associated permissions in Microsoft SQL Server.</span></span>  
  
 <span data-ttu-id="5b93e-106">Con el TPE, los administradores pueden:</span><span class="sxs-lookup"><span data-stu-id="5b93e-106">With TPE, administrators can:</span></span>  
  
-   <span data-ttu-id="5b93e-107">Recuperar un perfil de seguimiento activo asociado a uno o más ensamblados de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5b93e-107">Retrieve an active tracking profile associated with one or more assemblies from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="5b93e-108">Modificar el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5b93e-108">Modify the tracking profile</span></span>  
  
-   <span data-ttu-id="5b93e-109">Aplicar un perfil de seguimiento nuevo o modificado a la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5b93e-109">Apply a new or modified tracking profile into the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="5b93e-110">Modificar los archivos de perfiles seguimiento almacenados (.btt).</span><span class="sxs-lookup"><span data-stu-id="5b93e-110">Modify saved tracking profile files (.btt)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b93e-111">Los archivos de perfiles de seguimiento no determinan de forma definitiva el contenido de un perfil.</span><span class="sxs-lookup"><span data-stu-id="5b93e-111">Tracking profile files are not the final authority on the contents of a profile.</span></span> <span data-ttu-id="5b93e-112">El TPE puede guardar un perfil en un archivo, aunque primero extraerá y publicará el contenido de perfil en las bases de datos de BizTalk Server y de BAM.</span><span class="sxs-lookup"><span data-stu-id="5b93e-112">TPE can save a profile to a file, although it primarily pulls from and publishes the profile contents to the BizTalk Server and BAM databases.</span></span> <span data-ttu-id="5b93e-113">Los archivos de perfiles de seguimiento podrán seguir utilizándose para editar o actualizar el perfil almacenado, siempre que el contenido de archivo coincida con la información almacenada en las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5b93e-113">Tracking profile files can still be used to edit or update the stored profile as long as the file contents match the information stored in the databases.</span></span> <span data-ttu-id="5b93e-114">Además, los archivos de perfiles de seguimiento pueden organizarse en un paquete de aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5b93e-114">In addition, tracking profile files can be packaged within a BizTalk Server application package.</span></span> <span data-ttu-id="5b93e-115">Los paquetes de aplicaciones que incluyen archivos de perfiles de seguimiento invocan a BTTDeploy.exe para aplicar el perfil de seguimiento cuando el paquete MSI se importa a una determinada instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5b93e-115">Application packages that include tracking profile files automatically invoke BTTDeploy.exe to apply the tracking profile when the MSI package is imported to a given BizTalk Server installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5b93e-116">En el flujo de trabajo del TPE, y asumiendo que la programación y la implementación de tareas sean independientes (como es habitual), la persona responsable de la implementación deberá disponer de acceso de solo lectura al archivo .btt y al archivo de ensamblado asociado.</span><span class="sxs-lookup"><span data-stu-id="5b93e-116">In the TPE workflow, assuming the development and deployment tasks are separated, as is typically the case, the person responsible for deployment should have read-only access to the .btt file and the associated assembly file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b93e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b93e-117">See Also</span></span>  
 <span data-ttu-id="5b93e-118">[Flujo de trabajo BAM](../core/bam-workflow.md) </span><span class="sxs-lookup"><span data-stu-id="5b93e-118">[BAM Workflow](../core/bam-workflow.md) </span></span>  
 [<span data-ttu-id="5b93e-119">Editor de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5b93e-119">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)