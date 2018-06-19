---
title: Exportar Bindings6 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- exporting, bindings
ms.assetid: 052a429e-3237-44d4-8933-00aa5edfb212
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362984eca1dcec4fb68bfbac92c30da81de8a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246284"
---
# <a name="exporting-bindings"></a><span data-ttu-id="26043-102">Exportar enlaces</span><span class="sxs-lookup"><span data-stu-id="26043-102">Exporting Bindings</span></span>
<span data-ttu-id="26043-103">En los temas de esta sección se describe cómo exportar enlaces para un grupo, un ensamblado o una aplicación de BizTalk a un archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="26043-103">The topics in this section describe how to export bindings for a BizTalk group, assembly, or application into an .xml file.</span></span> <span data-ttu-id="26043-104">(Los enlaces definen cómo se asocian los hosts, puertos de envío, grupos de puertos de envío, puertos de recepción, ubicaciones de recepción y entidades con las orquestaciones, las canalizaciones, las asignaciones y los esquemas.) A continuación podrá importar los enlaces desde el archivo .xml a otro grupo o aplicación.</span><span class="sxs-lookup"><span data-stu-id="26043-104">(Bindings define how hosts, send ports, send port groups, receive ports, receive locations, parties are associated with orchestrations, pipelines, maps, and schemas.) You can then import the bindings from the .xml file into another group or application.</span></span> <span data-ttu-id="26043-105">Al importar enlaces se sobrescriben los enlaces existentes del mismo nombre en el grupo o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="26043-105">Importing bindings overwrites any existing bindings of the same name in the group or application.</span></span> <span data-ttu-id="26043-106">También puede agregar enlaces a una aplicación, con lo que no se sobrescriben los enlaces existentes.</span><span class="sxs-lookup"><span data-stu-id="26043-106">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="26043-107">Los enlaces que se agregan no se aplican hasta que se importa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="26043-107">The bindings that you add do not take effect until you import the application.</span></span>  
  
 <span data-ttu-id="26043-108">En los siguientes escenarios, podrá ver que el uso de archivos de enlace acelera la implementación, al evitar la necesidad de configurar los enlaces de forma manual:</span><span class="sxs-lookup"><span data-stu-id="26043-108">You may find that using binding files speeds application deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
-   <span data-ttu-id="26043-109">Mover una aplicación desde un entorno de implementación a otro.</span><span class="sxs-lookup"><span data-stu-id="26043-109">Moving an application from one deployment environment to another.</span></span>  
  
-   <span data-ttu-id="26043-110">Actualizar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="26043-110">Updating an assembly.</span></span>  
  
-   <span data-ttu-id="26043-111">Implementar un ensamblado junto con sus enlaces en varios grupos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="26043-111">Deploying an assembly together with its bindings to multiple BizTalk groups.</span></span>  
  
 <span data-ttu-id="26043-112">Para obtener más información acerca del uso de archivos de enlace para estos fines, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="26043-112">For more information about using binding files for these purposes, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
 <span data-ttu-id="26043-113">Para obtener más información sobre cómo importar y agregar enlaces, vea [cómo importar enlaces en un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md), [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md), y [cómo agregar un enlace Archivo a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md).</span><span class="sxs-lookup"><span data-stu-id="26043-113">For more information about importing and adding bindings, see [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md), [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md), and [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="26043-114">El archivo de enlace puede contener datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="26043-114">The binding file may contain sensitive data.</span></span> <span data-ttu-id="26043-115">Asegúrese de seguir los pasos necesarios proteger el archivo.</span><span class="sxs-lookup"><span data-stu-id="26043-115">Be sure to take steps to secure the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26043-116">Por motivos de seguridad, cuando exporte un archivo de enlace, BizTalk Server quita las contraseñas de los enlaces del archivo.</span><span class="sxs-lookup"><span data-stu-id="26043-116">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="26043-117">Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="26043-117">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="26043-118">Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="26043-118">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="26043-119">Para obtener instrucciones, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).</span><span class="sxs-lookup"><span data-stu-id="26043-119">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="26043-120">Vea también [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="26043-120">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26043-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="26043-121">In This Section</span></span>  
  
-   [<span data-ttu-id="26043-122">Cómo exportar enlaces para un grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="26043-122">How to Export Bindings for a BizTalk Group</span></span>](../core/how-to-export-bindings-for-a-biztalk-group.md)  
  
-   [<span data-ttu-id="26043-123">Cómo exportar enlaces para una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="26043-123">How to Export Bindings for a BizTalk Application</span></span>](../core/how-to-export-bindings-for-a-biztalk-application.md)  
  
-   [<span data-ttu-id="26043-124">Cómo exportar enlaces para un ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="26043-124">How to Export Bindings for a BizTalk Assembly</span></span>](../core/how-to-export-bindings-for-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="26043-125">Cómo exportar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="26043-125">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)